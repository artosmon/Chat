package ru.sberbank.uvz3.client.dataexporter.ui

import org.assertj.core.api.Assertions.assertThat
import org.junit.jupiter.api.Test
import org.mockito.kotlin.any
import org.mockito.kotlin.argumentCaptor
import org.mockito.kotlin.doReturn
import org.mockito.kotlin.eq
import org.mockito.kotlin.times
import org.mockito.kotlin.verify
import org.mockito.kotlin.whenever
import org.springframework.beans.factory.annotation.Autowired
import org.springframework.boot.resttestclient.autoconfigure.AutoConfigureRestTestClient
import org.springframework.boot.test.context.SpringBootTest
import org.springframework.http.HttpStatus
import org.springframework.http.ResponseEntity
import org.springframework.test.context.TestConstructor
import org.springframework.test.context.bean.override.mockito.MockitoBean
import org.springframework.test.context.bean.override.mockito.MockitoSpyBean
import org.springframework.test.web.servlet.client.RestTestClient
import org.springframework.web.client.RestTemplate
import ru.sberbank.uvz3.client.dataexporter.ControllerTestSupport
import ru.sberbank.uvz3.client.dataexporter.UnzippedFile
import ru.sberbank.uvz3.client.dictionary.agreement.AgreementStatus
import ru.sberbank.uvz3.client.dictionary.agreement.ProvisionType
import ru.sberbank.uvz3.client.dictionary.clientinfo.ClientType
import java.io.ByteArrayInputStream
import java.time.LocalDate

private const val CLIENT_ID_1 = "1"
private const val CLIENT_ID_2 = "2"
private const val CLIENT_ID_3 = "3"
private const val GENERAL_AGREEMENT_ID = "1001"
private const val CREDIT_AGREEMENT_ID = "2001"
private const val COLLATERAL_AGREEMENT_ID = "3001"
private const val GUARANTEE_AGREEMENT_ID = "4001"

@SpringBootTest(
    webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT,
    properties = ["client-data-exporter.export-from-ui.enabled=true"]
)
@TestConstructor(autowireMode = TestConstructor.AutowireMode.ALL)
@AutoConfigureRestTestClient
internal class FromUiFilesControllerTest : ControllerTestSupport() {

    @Autowired
    private lateinit var restTestClient: RestTestClient

    @MockitoSpyBean
    private lateinit var clientLoaderClient: ClientLoaderClient

    @MockitoBean
    private lateinit var restTemplate: RestTemplate

    @Test
    fun `вызываем load-clients-package-to-db`() {
        val clientsPackage: ClientsPackage = createPackage()

        whenever(
            restTemplate.postForEntity(
                eq("https://client-loader/api/v1/client/importData/bytes"),
                any(),
                eq(Long::class.java)
            )
        ) doReturn (ResponseEntity.ok(100))

        val captor = argumentCaptor<ByteArray>()

        // --- RestTestClient call ---
        val result: LoadClientsPackageResult =
            restTestClient.post()
                .uri("/api/v1/load-clients-package-to-db")
                .body(clientsPackage)
                .exchange()
                .expectStatus().isOk
                .expectBody(LoadClientsPackageResult::class.java)
                .returnResult()
                .responseBody
                ?: error("response body is null")

        assertThat(result.jobInstanceId).isEqualTo(100)
        assertThat(result.clientIds).isEqualTo(listOf("1", "2", "3"))

        verify(clientLoaderClient, times(1)).uploadClientsPackageToLoader(captor.capture())

        val bytes: ByteArray = captor.firstValue
        val byteArrayInputStream = ByteArrayInputStream(bytes)

        val files: List<UnzippedFile> = extractFiles(byteArrayInputStream)
        verifyFiles(files, "csv-expected-data/from-ui")
    }

    private fun createPackage(): ClientsPackage {
        val clients: List<NewClient> =
            listOf(
                NewClient(
                    id = CLIENT_ID_1,
                    type = ClientType.Person,
                    inn = "123456789012",
                    fullName = "Любимый клиент"
                ),
                NewClient(
                    id = CLIENT_ID_2,
                    type = ClientType.LegalEntity,
                    inn = "1234567890",
                    fullName = "Самый любимый клиент"
                ),
                NewClient(
                    id = CLIENT_ID_3,
                    type = ClientType.Individual,
                    inn = "210987654321",
                    fullName = "Нелюбимый клиент"
                )
            )

        val credits = listOf(
            NewCredit(
                id = CREDIT_AGREEMENT_ID,
                clientId = CLIENT_ID_1,
                agreementNumber = "creditAgr",
                agreementStatus = AgreementStatus.Working,
                generalAgreementId = GENERAL_AGREEMENT_ID
            )
        )

        val collateralToCredits = NewProvisionToCredits(
            creditId = CREDIT_AGREEMENT_ID,
            shareSum = "1000.0".toFloat(),
            mainCollatFlg = true
        )

        val collaterals: List<NewCollateral> = listOf(
            NewCollateral(
                id = COLLATERAL_AGREEMENT_ID,
                clientId = CLIENT_ID_1,
                agreementNumber = "123",
                agreementStatus = AgreementStatus.Working,
                collateralType = ProvisionType.Warranty,
                credits = listOf(collateralToCredits)
            )
        )

        val generals: List<NewGeneralAgreement> = listOf(
            NewGeneralAgreement(
                id = GENERAL_AGREEMENT_ID,
                clientId = CLIENT_ID_1,
                agreementNumber = "generalAgr",
                beginDate = LocalDate.parse("2023-06-29"),
                endingDate = LocalDate.parse("2024-06-29"),
                openDate = LocalDate.parse("2024-05-30"),
                closeDate = LocalDate.parse("2024-05-29")
            )
        )

        val guaranties = listOf(
            NewGuaranteeAgreement(
                id = GUARANTEE_AGREEMENT_ID,
                clientId = CLIENT_ID_2,
                agreementNumber = "789",
                beginDate = LocalDate.parse("2022-06-29"),
                endingDate = LocalDate.parse("2023-06-29"),
            )
        )

        return ClientsPackage(clients, credits, collaterals, generals, guaranties)
    }
}

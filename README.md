@Bean
public IntegrationFlow getAssetsOutboundGatewayFlow(RestTemplate pledgeHttpRestTemplate) {
    return prepareOutboundIntegrationFlow(GetPledgeIntegrationService.class, pledgeHttpRestTemplate, new ObjectFactory());
}


package ru.sberbank.uvz3.pledge.api.integration;

import org.springframework.transaction.annotation.Transactional;
import ru.sberbank.uvz3.pledge.http.GetAssetsObjectInfoRqType;
import ru.sberbank.uvz3.pledge.http.GetAssetsObjectInfoRsType;

import static org.springframework.transaction.annotation.Propagation.NOT_SUPPORTED;

@Transactional(propagation = NOT_SUPPORTED)
public interface GetPledgeIntegrationService {

    GetAssetsObjectInfoRsType getPledgeByClient(GetAssetsObjectInfoRqType getAssetsObjectInfoRq);
}



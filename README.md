plugins {
    id("ru.sberbank.uvz3.gradle.kotlin-spring-app")
}


dependencies {
    implementation(project(":client-data-exporter-liquibase"))
//    implementation("ru.sberbank.uvz3.client", "client-loader-core", "1.1.5")
    implementation("ru.sberbank.uvz3.client", "client-loader-core", "1.1.51")

    implementation(libs.clientDictionary)
    implementation("org.springframework.boot", "spring-boot-starter-web")
    implementation("org.springframework.boot", "spring-boot-starter-jdbc")
    implementation("org.springframework.cloud", "spring-cloud-commons")
    implementation("io.github.microutils", "kotlin-logging-jvm")

    compileOnly("io.micrometer:micrometer-tracing")

    developmentOnly("org.postgresql", "postgresql")

    productionOnly(project(":client-data-exporter-ui-new"))

    productionOnly("ru.sberbank.uvz3.cloud", "cloud-zookeeper-discovery-autoconfigure")
    productionOnly("ru.sberbank.uvz3.cloud", "cloud-starter-telemetry")
    productionOnly("ru.sberbank.uvz3.httpclient", "httpclient-ssl-okhttp-autoconfigure")
    productionOnly("ru.sberbank.uvz3.registrar", "registrar-meta-autoconfigure")

    // vault
    productionOnly("org.springframework.cloud:spring-cloud-starter-vault-config")

    productionOnly("org.postgresql", "postgresql")

    productionOnly("ru.sberbank.uvz3.databasemetrics:uvz-database-metrics")


    runtimeOnly("org.springframework.boot", "spring-boot-starter-actuator")
    runtimeOnly("org.glassfish.jaxb:jaxb-runtime")

    testImplementation("org.springframework.boot", "spring-boot-starter-test")
    testImplementation("org.mockito.kotlin", "mockito-kotlin")

    testImplementation("org.dbunit", "dbunit")
    testImplementation("com.github.springtestdbunit", "spring-test-dbunit", "1.3.0")

    developmentOnly("com.h2database", "h2")
    testImplementation("com.h2database", "h2")

}


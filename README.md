16:57:01: Executing ':client-data-exporter:dependencies --configuration compileClasspath'…


> Task :client-data-exporter:dependencies

------------------------------------------------------------
Project ':client-data-exporter'
------------------------------------------------------------

compileClasspath - Compile classpath for 'main'.
+--- io.micrometer:micrometer-tracing -> 1.6.2
|    +--- org.jspecify:jspecify:1.0.0
|    +--- io.micrometer:micrometer-observation:1.16.2
|    |    +--- org.jspecify:jspecify:1.0.0
|    |    \--- io.micrometer:micrometer-commons:1.16.2
|    |         \--- org.jspecify:jspecify:1.0.0
|    +--- io.micrometer:context-propagation:1.2.0
|    |    \--- org.jspecify:jspecify:1.0.0
|    \--- aopalliance:aopalliance:1.0
+--- org.jetbrains.kotlin:kotlin-stdlib -> 2.3.0
|    +--- org.jetbrains:annotations:13.0 -> 26.0.2-1
|    +--- org.jetbrains.kotlin:kotlin-stdlib-jdk8:1.8.0 -> 2.3.0 (c)
|    +--- org.jetbrains.kotlin:kotlin-stdlib-common:2.3.0 (c)
|    \--- org.jetbrains.kotlin:kotlin-stdlib-jdk7:1.8.0 -> 2.3.0 (c)
+--- org.jetbrains.kotlin:kotlin-reflect -> 2.3.0
|    \--- org.jetbrains.kotlin:kotlin-stdlib:2.3.0 (*)
+--- project :client-data-exporter-liquibase
+--- ru.sberbank.uvz3.client:client-loader-core:1.1.51
+--- ru.sberbank.uvz3.client:client-dictionary:2.0.23
+--- org.springframework.boot:spring-boot-starter-web -> 4.0.2
|    +--- org.springframework.boot:spring-boot-starter-jackson:4.0.2
|    |    +--- org.springframework.boot:spring-boot-starter:4.0.2
|    |    |    +--- org.springframework.boot:spring-boot-starter-logging:4.0.2
|    |    |    |    +--- ch.qos.logback:logback-classic:1.5.25
|    |    |    |    |    +--- ch.qos.logback:logback-core:1.5.25
|    |    |    |    |    \--- org.slf4j:slf4j-api:2.0.17
|    |    |    |    +--- org.apache.logging.log4j:log4j-to-slf4j:2.25.3
|    |    |    |    |    +--- org.apache.logging.log4j:log4j-api:2.25.3
|    |    |    |    |    |    +--- org.jspecify:jspecify:1.0.0
|    |    |    |    |    |    +--- biz.aQute.bnd:biz.aQute.bnd.annotation:7.1.0
|    |    |    |    |    |    |    +--- org.osgi:org.osgi.resource:1.0.0
|    |    |    |    |    |    |    \--- org.osgi:org.osgi.service.serviceloader:1.0.0
|    |    |    |    |    |    +--- com.google.errorprone:error_prone_annotations:2.38.0 -> 2.41.0
|    |    |    |    |    |    +--- org.osgi:org.osgi.annotation.bundle:2.0.0
|    |    |    |    |    |    |    \--- org.osgi:org.osgi.annotation.versioning:1.1.2
|    |    |    |    |    |    \--- org.osgi:org.osgi.annotation.versioning:1.1.2
|    |    |    |    |    +--- org.slf4j:slf4j-api:2.0.17
|    |    |    |    |    +--- org.jspecify:jspecify:1.0.0
|    |    |    |    |    +--- biz.aQute.bnd:biz.aQute.bnd.annotation:7.1.0 (*)
|    |    |    |    |    +--- com.google.errorprone:error_prone_annotations:2.38.0 -> 2.41.0
|    |    |    |    |    +--- org.osgi:org.osgi.annotation.bundle:2.0.0 (*)
|    |    |    |    |    \--- org.osgi:org.osgi.annotation.versioning:1.1.2
|    |    |    |    \--- org.slf4j:jul-to-slf4j:2.0.17
|    |    |    |         \--- org.slf4j:slf4j-api:2.0.17
|    |    |    +--- org.springframework.boot:spring-boot-autoconfigure:4.0.2
|    |    |    |    \--- org.springframework.boot:spring-boot:4.0.2
|    |    |    |         +--- org.springframework:spring-core:7.0.3
|    |    |    |         |    +--- commons-logging:commons-logging:1.3.5
|    |    |    |         |    \--- org.jspecify:jspecify:1.0.0
|    |    |    |         \--- org.springframework:spring-context:7.0.3
|    |    |    |              +--- org.springframework:spring-aop:7.0.3
|    |    |    |              |    +--- org.springframework:spring-beans:7.0.3
|    |    |    |              |    |    \--- org.springframework:spring-core:7.0.3 (*)
|    |    |    |              |    \--- org.springframework:spring-core:7.0.3 (*)
|    |    |    |              +--- org.springframework:spring-beans:7.0.3 (*)
|    |    |    |              +--- org.springframework:spring-core:7.0.3 (*)
|    |    |    |              +--- org.springframework:spring-expression:7.0.3
|    |    |    |              |    \--- org.springframework:spring-core:7.0.3 (*)
|    |    |    |              \--- io.micrometer:micrometer-observation:1.16.2 (*)
|    |    |    +--- jakarta.annotation:jakarta.annotation-api:3.0.0
|    |    |    \--- org.yaml:snakeyaml:2.5
|    |    \--- org.springframework.boot:spring-boot-jackson:4.0.2
|    |         +--- org.springframework.boot:spring-boot:4.0.2 (*)
|    |         \--- tools.jackson.core:jackson-databind:3.0.4
|    |              +--- com.fasterxml.jackson.core:jackson-annotations:2.20
|    |              +--- tools.jackson.core:jackson-core:3.0.4
|    |              |    \--- tools.jackson:jackson-bom:3.0.4
|    |              |         +--- com.fasterxml.jackson.core:jackson-annotations:2.20 (c)
|    |              |         +--- tools.jackson.core:jackson-core:3.0.4 (c)
|    |              |         \--- tools.jackson.core:jackson-databind:3.0.4 (c)
|    |              \--- tools.jackson:jackson-bom:3.0.4 (*)
|    +--- org.springframework.boot:spring-boot-starter-tomcat:4.0.2
|    |    +--- org.springframework.boot:spring-boot-starter:4.0.2 (*)
|    |    +--- org.springframework.boot:spring-boot-starter-tomcat-runtime:4.0.2
|    |    |    +--- org.springframework.boot:spring-boot-tomcat:4.0.2
|    |    |    |    +--- org.springframework.boot:spring-boot-web-server:4.0.2
|    |    |    |    |    +--- org.springframework.boot:spring-boot:4.0.2 (*)
|    |    |    |    |    \--- org.springframework:spring-web:7.0.3
|    |    |    |    |         +--- org.springframework:spring-beans:7.0.3 (*)
|    |    |    |    |         +--- org.springframework:spring-core:7.0.3 (*)
|    |    |    |    |         \--- io.micrometer:micrometer-observation:1.16.2 (*)
|    |    |    |    \--- org.apache.tomcat.embed:tomcat-embed-core:11.0.15
|    |    |    +--- org.springframework.boot:spring-boot-web-server:4.0.2 (*)
|    |    |    +--- jakarta.annotation:jakarta.annotation-api:3.0.0
|    |    |    +--- org.apache.tomcat.embed:tomcat-embed-core:11.0.15
|    |    |    +--- org.apache.tomcat.embed:tomcat-embed-el:11.0.15
|    |    |    \--- org.apache.tomcat.embed:tomcat-embed-websocket:11.0.15
|    |    |         \--- org.apache.tomcat.embed:tomcat-embed-core:11.0.15
|    |    \--- org.springframework.boot:spring-boot-tomcat:4.0.2 (*)
|    +--- org.springframework.boot:spring-boot-http-converter:4.0.2
|    |    +--- org.springframework.boot:spring-boot:4.0.2 (*)
|    |    \--- org.springframework:spring-web:7.0.3 (*)
|    \--- org.springframework.boot:spring-boot-webmvc:4.0.2
|         +--- org.springframework.boot:spring-boot-servlet:4.0.2
|         |    +--- org.springframework.boot:spring-boot:4.0.2 (*)
|         |    \--- org.springframework:spring-web:7.0.3 (*)
|         +--- org.springframework:spring-web:7.0.3 (*)
|         \--- org.springframework:spring-webmvc:7.0.3
|              +--- org.springframework:spring-aop:7.0.3 (*)
|              +--- org.springframework:spring-beans:7.0.3 (*)
|              +--- org.springframework:spring-context:7.0.3 (*)
|              +--- org.springframework:spring-core:7.0.3 (*)
|              +--- org.springframework:spring-expression:7.0.3 (*)
|              \--- org.springframework:spring-web:7.0.3 (*)
+--- org.springframework.boot:spring-boot-starter-jdbc -> 4.0.2
|    +--- org.springframework.boot:spring-boot-starter:4.0.2 (*)
|    +--- org.springframework.boot:spring-boot-jdbc:4.0.2
|    |    +--- org.springframework.boot:spring-boot:4.0.2 (*)
|    |    +--- org.springframework.boot:spring-boot-sql:4.0.2
|    |    |    \--- org.springframework.boot:spring-boot:4.0.2 (*)
|    |    +--- org.springframework.boot:spring-boot-transaction:4.0.2
|    |    |    +--- org.springframework.boot:spring-boot:4.0.2 (*)
|    |    |    +--- org.springframework.boot:spring-boot-persistence:4.0.2
|    |    |    |    +--- org.springframework.boot:spring-boot:4.0.2 (*)
|    |    |    |    \--- org.springframework:spring-tx:7.0.3
|    |    |    |         +--- org.springframework:spring-beans:7.0.3 (*)
|    |    |    |         \--- org.springframework:spring-core:7.0.3 (*)
|    |    |    \--- org.springframework:spring-tx:7.0.3 (*)
|    |    \--- org.springframework:spring-jdbc:7.0.3
|    |         +--- org.springframework:spring-beans:7.0.3 (*)
|    |         +--- org.springframework:spring-core:7.0.3 (*)
|    |         \--- org.springframework:spring-tx:7.0.3 (*)
|    \--- com.zaxxer:HikariCP:7.0.2
|         \--- org.slf4j:slf4j-api:2.0.17
+--- org.springframework.cloud:spring-cloud-commons -> 5.0.0
|    \--- org.springframework.security:spring-security-crypto:7.0.0 -> 7.0.2
+--- io.github.microutils:kotlin-logging-jvm -> 3.0.5
|    +--- org.slf4j:slf4j-api:2.0.3 -> 2.0.17
|    +--- org.jetbrains.kotlin:kotlin-stdlib-jdk8:1.8.0 -> 2.3.0
|    |    +--- org.jetbrains.kotlin:kotlin-stdlib:2.3.0 (*)
|    |    \--- org.jetbrains.kotlin:kotlin-stdlib-jdk7:2.3.0
|    |         \--- org.jetbrains.kotlin:kotlin-stdlib:2.3.0 (*)
|    \--- org.jetbrains.kotlin:kotlin-stdlib-common:1.8.0 -> 2.3.0
|         \--- org.jetbrains.kotlin:kotlin-stdlib:2.3.0 (*)
+--- org.jetbrains.kotlin:kotlin-stdlib:2.3.0 (c)
+--- org.jetbrains.kotlin:kotlin-reflect:2.3.0 (c)
+--- org.jetbrains.kotlin:kotlin-bom:2.3.0
|    +--- org.jetbrains.kotlin:kotlin-stdlib:2.3.0 (c)
|    +--- org.jetbrains.kotlin:kotlin-reflect:2.3.0 (c)
|    +--- org.jetbrains.kotlin:kotlin-stdlib-jdk8:2.3.0 (c)
|    +--- org.jetbrains.kotlin:kotlin-stdlib-common:2.3.0 (c)
|    \--- org.jetbrains.kotlin:kotlin-stdlib-jdk7:2.3.0 (c)
+--- org.springframework.boot:spring-boot-dependencies:4.0.2
|    +--- org.jetbrains.kotlin:kotlin-stdlib:2.2.21 -> 2.3.0 (c)
|    +--- org.jetbrains.kotlin:kotlin-reflect:2.2.21 -> 2.3.0 (c)
|    +--- io.micrometer:micrometer-tracing:1.6.2 (c)
|    +--- org.springframework.boot:spring-boot-starter-jdbc:4.0.2 (c)
|    +--- org.springframework.boot:spring-boot-starter-web:4.0.2 (c)
|    +--- org.jspecify:jspecify:1.0.0 (c)
|    +--- io.micrometer:micrometer-observation:1.16.2 (c)
|    +--- io.micrometer:context-propagation:1.2.0 (c)
|    +--- org.springframework.boot:spring-boot-starter:4.0.2 (c)
|    +--- org.springframework.boot:spring-boot-jdbc:4.0.2 (c)
|    +--- com.zaxxer:HikariCP:7.0.2 (c)
|    +--- org.springframework.boot:spring-boot-starter-jackson:4.0.2 (c)
|    +--- org.springframework.boot:spring-boot-starter-tomcat:4.0.2 (c)
|    +--- org.springframework.boot:spring-boot-http-converter:4.0.2 (c)
|    +--- org.springframework.boot:spring-boot-webmvc:4.0.2 (c)
|    +--- org.springframework.security:spring-security-crypto:7.0.2 (c)
|    +--- org.slf4j:slf4j-api:2.0.17 (c)
|    +--- org.jetbrains.kotlin:kotlin-stdlib-jdk8:2.2.21 -> 2.3.0 (c)
|    +--- org.jetbrains.kotlin:kotlin-stdlib-common:2.2.21 -> 2.3.0 (c)
|    +--- io.micrometer:micrometer-commons:1.16.2 (c)
|    +--- org.springframework.boot:spring-boot-starter-logging:4.0.2 (c)
|    +--- org.springframework.boot:spring-boot-autoconfigure:4.0.2 (c)
|    +--- jakarta.annotation:jakarta.annotation-api:3.0.0 (c)
|    +--- org.yaml:snakeyaml:2.5 (c)
|    +--- org.springframework.boot:spring-boot:4.0.2 (c)
|    +--- org.springframework.boot:spring-boot-sql:4.0.2 (c)
|    +--- org.springframework.boot:spring-boot-transaction:4.0.2 (c)
|    +--- org.springframework:spring-jdbc:7.0.3 (c)
|    +--- org.springframework.boot:spring-boot-jackson:4.0.2 (c)
|    +--- org.springframework.boot:spring-boot-starter-tomcat-runtime:4.0.2 (c)
|    +--- org.springframework.boot:spring-boot-tomcat:4.0.2 (c)
|    +--- org.springframework:spring-web:7.0.3 (c)
|    +--- org.springframework.boot:spring-boot-servlet:4.0.2 (c)
|    +--- org.springframework:spring-webmvc:7.0.3 (c)
|    +--- org.jetbrains.kotlin:kotlin-stdlib-jdk7:2.2.21 -> 2.3.0 (c)
|    +--- ch.qos.logback:logback-classic:1.5.25 (c)
|    +--- org.apache.logging.log4j:log4j-to-slf4j:2.25.3 (c)
|    +--- org.slf4j:jul-to-slf4j:2.0.17 (c)
|    +--- org.springframework:spring-core:7.0.3 (c)
|    +--- org.springframework:spring-context:7.0.3 (c)
|    +--- org.springframework.boot:spring-boot-persistence:4.0.2 (c)
|    +--- org.springframework:spring-tx:7.0.3 (c)
|    +--- org.springframework:spring-beans:7.0.3 (c)
|    +--- tools.jackson.core:jackson-databind:3.0.4 (c)
|    +--- org.springframework.boot:spring-boot-web-server:4.0.2 (c)
|    +--- org.apache.tomcat.embed:tomcat-embed-core:11.0.15 (c)
|    +--- org.apache.tomcat.embed:tomcat-embed-el:11.0.15 (c)
|    +--- org.apache.tomcat.embed:tomcat-embed-websocket:11.0.15 (c)
|    +--- org.springframework:spring-aop:7.0.3 (c)
|    +--- org.springframework:spring-expression:7.0.3 (c)
|    +--- ch.qos.logback:logback-core:1.5.25 (c)
|    +--- org.apache.logging.log4j:log4j-api:2.25.3 (c)
|    +--- commons-logging:commons-logging:1.3.5 (c)
|    +--- com.fasterxml.jackson.core:jackson-annotations:2.20 (c)
|    \--- tools.jackson.core:jackson-core:3.0.4 (c)
+--- org.springframework.cloud:spring-cloud-dependencies:2025.1.0
|    \--- org.springframework.cloud:spring-cloud-commons:5.0.0 (c)
\--- ru.sberbank.uvz3:uvz-platform:latest.release -> 2.1-3537
     +--- com.google.guava:guava-parent:33.5.0-jre
     |    +--- org.jspecify:jspecify:1.0.0 (c)
     |    \--- com.google.errorprone:error_prone_annotations:2.41.0 (c)
     +--- ru.sberbank.uvz3.jimmer:jimmer-bom:0.10.5.1
     +--- ru.sberbank.uvz3.jimmer:jimmer-ext-platform:1.1.12
     +--- ru.sberbank.uvz3.lightmin:spring-batch-lightmin-bom:4.1.0
     +--- org.testcontainers:testcontainers-bom:2.0.3
     +--- ru.sberbank.uvz2.component:sudir-security-platform:4.1.0
     +--- ru.sberbank.uvz3.security:uvz-security-gateway-platform:4.2.0
     +--- ru.sberbank.uvz2.library:integration-adapter-platform:4.1.0
     +--- ru.sberbank.uvz2.library:tfs-adapter-platform:5.1.0
     +--- ru.sberbank.uvz2.library:ecm-adapter-platform:5.6.0
     +--- ru.sberbank.uvz2.module:step-machine-platform:2.0.9
     +--- ru.sberbank.uvz3.acl:acl-bom:2.1.0
     +--- ru.sberbank.uvz3.library.aeadapter:ae-adapter-platform:1.0.11
     +--- ru.sberbank.uvz3.library.ccaadapter:cca-adapter-platform:1.1.9
     +--- ru.sberbank.uvz3.library.uod:uod-adapter-platform:1.0.0
     +--- ru.sberbank.uvz3.aoplogging:aop-logging-platform:2.0.2
     +--- ru.sberbank.uvz3.audit:uvz-audit-platform:2.4.0
     +--- ru.sberbank.uvz3.client:client-facade-platform:2.2.0
     +--- ru.sberbank.uvz3.cloud:cloud-platform:2.3.0
     +--- ru.sberbank.uvz3.dictionary:dictionary-bom:2.1.0
     +--- ru.sberbank.uvz3.email.emailadapter:email-adapter-platform:3.0.10
     +--- ru.sberbank.uvz3.eventstore:event-store-bom:2.1.0
     +--- ru.sberbank.uvz3.extspring:ext-spring-platform:3.3.0
     +--- ru.sberbank.uvz3:ssl-config-platform:2.0.2
     +--- ru.sberbank.uvz3.gsz:gsz-platform:2.2.0
     +--- ru.sberbank.uvz3.jacksonmodules:jackson-modules-platform:2.1.0
     +--- ru.sberbank.uvz3.jmsendpoints:jms-endpoints-platform:2.1.0
     +--- ru.sberbank.uvz3.hibernatesupport:hibernate-support-platform:2.1.3
     +--- ru.sberbank.uvz3.library:fok-adapter-platform:3.3.8
     +--- ru.sberbank.uvz3.library:fns-adapter-platform:2.0.2
     +--- com.google.protobuf:protobuf-bom:4.32.1
     +--- ru.sberbank.uvz3.library.qdsl:ext-query-dsl-platform:2.1.0
     +--- ru.sberbank.uvz3.ott.cloud:ott-client-platform:1.0.4
     +--- ru.sberbank.uvz3.module.orgstructure:orgstructure-service-platform:3.1.0
     +--- ru.sberbank.uvz3.org-structure:org-structure-platform:3.4.8
     +--- ru.sberbank.uvz3.library.pgwadapter:pgw-adapter-platform:2.1.0
     +--- ru.sberbank.uvz3.pledges:pledges-facade-platform:1.1.6
     +--- ru.sberbank.uvz3.library.pprbstatementadapter:pprb-statement-adapter-platform:1.3.5
     +--- ru.sberbank.uvz3.problemasset:problem-asset-facade-platform:4.1.74
     +--- ru.sberbank.uvz3.module.russianpost:russian-post-service-api-platform:1.0.28
     +--- ru.sberbank.uvz3.returnplan:return-plan-api-platform:3.1.0
     +--- ru.sberbank.uvz3.sqldsl:sql-dsl-platform:2.1.2
     +--- ru.sberbank.uvz3.taskmanager:task-manager-platform:2.4.0
     +--- ru.sberbank.uvz3.uvztaskmanager:uvz-task-manager-platform:2.4.0
     +--- ru.sberbank.uvz3.transactionaloutbox:transactional-outbox-platform:2.0.2
     +--- ru.sberbank.uvz3.stoplistadapter:stoplist-adapter-platform:2.0.2
     +--- ru.sberbank.uvz3.marketplace:marketplace-adapter-platform:3.1.2
     +--- ru.sberbank.uvz3.senat:senat-adapter-platform:5.0.16
     +--- ru.sberbank.uvz3.servicerequest:service-request-platform:1.11.0
     +--- ru.sberbank.uvz3.sudiradapter:sudir-adapter-platform:2.1.3
     +--- ru.sberbank.uvz3.library.commondictionaries:common-dictionaries-platform:1.0.18
     +--- ru.sberbank.uvz3.contentmanager:content-manager-platform:1.6.0
     +--- ru.sberbank.uvz3.uvzcontentmanager:uvz-content-manager-platform:1.2.18
     +--- ru.sberbank.uvz3.ott.client:uvz-ott-client-platform:1.0.12
     +--- ru.sberbank.uvz3.expression:expression-platform:1.3.1
     +--- ru.sberbank.uvz3.office.templater:office-templater-platform:2.4.1
     +--- ru.sberbank.uvz3.l4b.adapter:l4b-adapter-platform:1.10.0
     +--- ru.sberbank.uvz3.library.legaladapter:legal-adapter-platform:1.1.0
     +--- ru.sberbank.uvz3.bbb:bbb-platform:0.1.35
     +--- ru.sberbank.uvz3.schedulex:schedulex-platform:1.6.15
     +--- ru.sberbank.uvz3.dbcounter:dbcounter-platform:1.0.0
     +--- ru.sberbank.uvz3.sudir:scim-agent-platform:1.2.10
     +--- ru.sberbank.uvz3.sberbusiness:sberbusiness-adapter-platform:1.1.1
     +--- ru.sberbank.uvz3.library:reserves-adapter-platform:1.2.7
     +--- ru.sberbank.uvz3.module.calendarwidget:calendar-widget-platform:1.0.22
     +--- com.squareup.okhttp3:okhttp-bom:4.12.0
     +--- ru.sberbank.uvz3.documentservice:document-service-platform:1.1.7
     +--- ru.sberbank.uvz3.integrationlog:integration-log-platform:1.1.0
     +--- ru.sberbank.uvz3.library.deviationreactions:deviation-reactions-platform:1.0.21
     +--- ru.sberbank.uvz3.library.egrulegripreport:egrul-egrip-fns-report-platform:0.0.15
     +--- ru.sberbank.uvz3.client:client-dictionary:2.0.23 (c)
     +--- io.github.microutils:kotlin-logging-jvm:3.0.5 (c)
     \--- org.jetbrains:annotations:26.0.2-1 (c)

(c) - A dependency constraint, not a dependency. The dependency affected by the constraint occurs elsewhere in the tree.
(*) - Indicates repeated occurrences of a transitive dependency subtree. Gradle expands transitive dependency subtrees only once per project; repeat occurrences only display the root of the subtree, followed by this annotation.

A web-based, searchable dependency report is available by adding the --scan option.

[Incubating] Problems report is available at: file:///C:/Work/uvz/client-data-exporter/build/reports/problems/problems-report.html

Deprecated Gradle features were used in this build, making it incompatible with Gradle 10.

You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.

For more on this, please refer to https://docs.gradle.org/9.2.1/userguide/command_line_interface.html#sec:command_line_warnings in the Gradle documentation.

BUILD SUCCESSFUL in 4s
1 actionable task: 1 executed
Consider enabling configuration cache to speed up this build: https://docs.gradle.org/9.2.1/userguide/configuration_cache_enabling.html
16:57:06: Execution finished ':client-data-exporter:dependencies --configuration compileClasspath'.

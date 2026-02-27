Caused by: java.lang.NoClassDefFoundError: com/fasterxml/jackson/databind/ObjectMapper
	at org.springframework.jms.support.converter.MappingJackson2MessageConverter.<init>(MappingJackson2MessageConverter.java:96)
	at ru.sberbank.uvz3.client.epk.facade.EpkIntegrationJmsConfiguration.epkMessageConverter(EpkIntegrationJmsConfiguration.java:56)
	at java.base/java.lang.reflect.Method.invoke(Method.java:580)
	at org.springframework.beans.factory.support.SimpleInstantiationStrategy.lambda$instantiate$0(SimpleInstantiationStrategy.java:155)
	... 64 more

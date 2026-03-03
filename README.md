    private StandardIntegrationFlow prepareOutboundIntegrationFlow(Class<?> serviceInterface, RestTemplate updatePledgeHttpRestTemplate, Object... objectFactory) {
        Jaxb2WrapperImpl wrapper = new Jaxb2WrapperImpl();
        Arrays.stream(objectFactory).forEach(wrapper::scanWrappingFunctions);
        return IntegrationFlow.from(serviceInterface)
                .transform(new WrappingMessageTransformer(wrapper))
                .log(LoggingHandler.Level.INFO, PLEDGE_ADAPTER_SYNAPSE_OUTBOUND_LOGGER)
                .enrichHeaders(h -> h.header(HttpHeaders.CONTENT_TYPE, MediaType.APPLICATION_XML_VALUE))
                .handle(
                        Http.outboundGateway(defineUri(), updatePledgeHttpRestTemplate)
                                .expectedResponseType(JAXBElement.class))
                .log(LoggingHandler.Level.INFO, PLEDGE_ADAPTER_SYNAPSE_INBOUND_LOGGER)
                .transform(new UnwrappingMessageTransformer(wrapper))
                .get();
    }

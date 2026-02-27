    @Bean
    @ConditionalOnMissingBean
    MessageConverter epkMessageConverter() {
        var converter = new MappingJackson2MessageConverter();
        converter.setTargetType(MessageType.TEXT);
        converter.setTypeIdPropertyName(OBJECT_TYPE);
        converter.setTypeIdMappings(Collections.singletonMap(EpkIdResponse.class.getName(), EpkIdResponse.class));
        return converter;
    }

object MessageConverterProvider {
    val OBJECT_TYPE = "object_type"

    fun getMessageConverter(): MessageConverter {
        val converter = MappingJackson2MessageConverter()
        converter.setTargetType(MessageType.TEXT)
        converter.setTypeIdPropertyName(OBJECT_TYPE)
        return converter
    }
}

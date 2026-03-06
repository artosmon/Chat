import org.springframework.jms.support.converter.Jackson2JsonMessageConverter
import org.springframework.jms.support.converter.MessageConverter
import org.springframework.jms.support.converter.MessageType

object MessageConverterProvider {

    const val OBJECT_TYPE = "object_type"

    fun getMessageConverter(): MessageConverter {
        val converter = Jackson2JsonMessageConverter()
        converter.setTargetType(MessageType.TEXT)
        converter.setTypeIdPropertyName(OBJECT_TYPE)
        return converter
    }
}

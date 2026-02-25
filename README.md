    @Bean
    @ConditionalOnMissingBean(name = ["metaRestTemplate"])
    fun metaRestTemplate(
        restTemplateBuilder: RestTemplateBuilder,
        restTemplateCustomizer: ObjectProvider<RestTemplateCustomizer>
    ): RestTemplate {

        val restTemplate = restTemplateBuilder.build()
        restTemplateCustomizer.ifAvailable { c: RestTemplateCustomizer ->
            c.customize(
                restTemplate
            )
        }
        return restTemplate
    }

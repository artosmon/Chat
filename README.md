        restTemplateCustomizer.ifAvailable { c: RestTemplateCustomizer ->
                c.customize(
                        restTemplate
                )
        }

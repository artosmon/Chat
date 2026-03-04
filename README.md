package ru.sberbank.uvz3.pledges.config;

import com.github.kagkarlsson.scheduler.boot.config.DbSchedulerCustomizer;
import com.github.kagkarlsson.scheduler.serializer.JacksonSerializer;
import com.github.kagkarlsson.scheduler.serializer.Serializer;
import org.hibernate.cfg.AvailableSettings;
import org.hibernate.type.format.jackson.JacksonJsonFormatMapper;
import org.springframework.boot.context.properties.EnableConfigurationProperties;
import org.springframework.boot.hibernate.autoconfigure.HibernatePropertiesCustomizer;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.scheduling.annotation.EnableScheduling;
import ru.sberbank.uvz3.cloud.core.leader.scheduling.EnableSchedulingOnLeader;
import ru.sberbank.uvz3.dictionary.registry.DictionaryRegistryConfigurer;
import ru.sberbank.uvz3.pledge.api.bussiness.model.dictionary.RealizationStatus;
import ru.sberbank.uvz3.pledges.application.service.sberfriend.SberfriendProperties;
import ru.sberbank.uvz3.pledges.domain.LotOriginType;
import tools.jackson.databind.ObjectMapper;

import java.util.Optional;

@Configuration
@EnableScheduling
@EnableSchedulingOnLeader
@EnableConfigurationProperties(SberfriendProperties.class)
public class RootConfig {

    @Bean
    DictionaryRegistryConfigurer dictionaryRegistryConfigurer() {
        return registry -> registry
                .addEnumRepository(RealizationStatus.class)
                .addEnumRepository(LotOriginType.class);
    }

    @Bean
    public DbSchedulerCustomizer dbSchedulerCustomizer(ObjectMapper objectMapper) {
        return new DbSchedulerCustomizer() {
            @Override
            public Optional<Serializer> serializer() {
                return Optional.of(new JacksonSerializer(objectMapper));
            }
        };
    }

    @Bean
    public HibernatePropertiesCustomizer jsonFormatMapper(final ObjectMapper objectMapper) {
        return properties -> properties.put(AvailableSettings.JSON_FORMAT_MAPPER, new JacksonJsonFormatMapper(objectMapper));
    }
}

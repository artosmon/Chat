package ru.sberbank.uvz3.pledges.application.service.aiagent;

import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.databind.PropertyNamingStrategies;
import com.fasterxml.jackson.databind.json.JsonMapper;
import org.junit.jupiter.api.Test;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.core.io.ClassPathResource;
import org.springframework.http.MediaType;
import org.springframework.test.web.servlet.MockMvc;
import org.springframework.test.web.servlet.request.MockMvcRequestBuilders;
import org.springframework.util.StreamUtils;
import ru.sberbank.uvz3.pledges.application.port.in.AiAgentProvider;
import ru.sberbank.uvz3.pledges.support.BaseTestSupport;

import java.nio.charset.StandardCharsets;

import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.content;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.status;

class AiAgentProviderTest extends BaseTestSupport {
    @Autowired
    MockMvc mockMvc;
    @Autowired
    ObjectMapper objectMapper;

    @Test
    void getDataByClientIdTest() throws Exception {
        var mapper = objectMapper.copy().setPropertyNamingStrategy(PropertyNamingStrategies.SNAKE_CASE);

        mockMvc.perform(MockMvcRequestBuilders.post("/external-api/ai-agent/get-data-by-client-id")
                        .contentType(MediaType.APPLICATION_JSON)
                        .content(mapper.writeValueAsString(new AiAgentProvider.GetDataByClientIdInput("PROVISIONER"))
                        ))
                .andExpect(status().isOk())
                .andExpect(content().json(StreamUtils.copyToString(new ClassPathResource("json/get-data-by-client-ai-agent-responce.json").getInputStream(), StandardCharsets.UTF_8)));
    }
}

@RestController
@RequestMapping("/external-api/ai-agent")
@RequiredArgsConstructor
public class AiAgentController {
    private final AiAgentProvider provider;

    @PostMapping("/get-data-by-client-id")
    public Set<AiAgentProvider.PledgeDto> getPublicationById(@RequestBody AiAgentProvider.GetDataByClientIdInput input) {
        return provider.getDataByClientId(input);
    }
}

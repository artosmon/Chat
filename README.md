public interface AiAgentProvider {

    Set<PledgeDto> getDataByClientId(GetDataByClientIdInput request);

    @JsonNaming(PropertyNamingStrategies.SnakeCaseStrategy.class)
    record GetDataByClientIdInput(@NotNull String clientId) {
    }

    @JsonNaming(PropertyNamingStrategies.SnakeCaseStrategy.class)
    @Builder
    record PledgeDto(String pledgeAssetType, BigDecimal pledgeAssetCost) {
    }
}

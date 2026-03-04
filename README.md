    @Bean
    @DependsOn({"getAssetsOutboundGatewayFlow", "updateAssetsOutboundGatewayFlow", "putUniversalApplicationOutboundGatewayFlow"})
    public PledgeService pledgeService(GetPledgeIntegrationService getPledgeIntegrationService,
                                       UpdatePledgeIntegrationService updatePledgeIntegrationService,
                                       PutUniversalApplicationPledgeIntegrationService universalIntegrationService,
                                       GetAssetsObjectMapper mapper,
                                       PutAssetObjectMapper putAssetObjectMapper,
                                       PutUniversalApplicationMapper universalApplicationMapper) {
        return new HttpPledgeIntegrationService(
                getPledgeIntegrationService,
                updatePledgeIntegrationService,
                universalIntegrationService,
                mapper,
                putAssetObjectMapper,
                universalApplicationMapper);
    }

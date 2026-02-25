    private fun fetchClientIdsFromDG(clientIds: List<String>): List<String> {
        val result: ArrayList<String> = arrayListOf()
        val valuesSize = clientIds.size
        var tmpParamsSize = 0

        while (tmpParamsSize < valuesSize) {

            val toIndex = if (tmpParamsSize + maxParamsSize < valuesSize) {
                tmpParamsSize + maxParamsSize
            } else {
                valuesSize
            }

            val parameterSource =
                MapSqlParameterSource(mapOf("client_ids" to clientIds.subList(tmpParamsSize, toIndex)))
            result.addAll(
                jdbcTemplate.queryForList(
                    "SELECT collateral_client_id FROM $clientLoaderSchema.debtors_group WHERE credit_agreement_client_id IN (:client_ids)",
                    parameterSource,
                    String::class.java
                )
            )
            tmpParamsSize = toIndex
        }

        return result
    }

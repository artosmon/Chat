    fun readValue(id: String): String? {
        val list: List<Map<String, Any>> = namedParametersJdbcTemplate.queryForList(
            """
                SELECT value
                FROM internal_data
                WHERE id = :id
            """.trimIndent(),

            mapOf("id" to id)
        )

        return list.firstOrNull()?.get("value") as String?
    }

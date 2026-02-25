    fun `вызываем exportData (есть данные в БД)`() {
        val response: ResponseEntity<ByteArray> =
            testRestTemplate.getForEntity("/api/v1/client/clientId/exportData", ByteArray::class.java)

        assertThat(response.statusCode).isEqualTo(HttpStatus.OK)

        val bis = BufferedInputStream(response.body!!.inputStream());

        val files: List<UnzippedFile> = extractFiles(bis)
        verifyFiles(files, "csv-expected-data/from-db/common/single", "csv-expected-data/from-db/uvz/single")
    }

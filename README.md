    protected fun verifyFiles(files: List<UnzippedFile>, vararg directories: String) {
        files.forEach {
            //            println("file name: ${it.filename}")
            //            println("file content:\n ${decompress(it.content)}")
            //
            val compressedFile = File(tmpDir.toFile(), it.filename)
            compressedFile.writeBytes(it.content)

            var expectedFileName = ""
            for (directory in directories) {
                expectedFileName = "$directory/${it.filename}".dropLast(".gz".length)
                if (ClassPathResource(expectedFileName).exists()) {
                    break
                }
            }

            val actualCsv: String = decompress(compressedFile)
            val expectedCsv: String =
                StreamUtils.copyToString(ClassPathResource(expectedFileName).inputStream, Charsets.UTF_8)

            Assertions.assertThat(actualCsv).isEqualTo(expectedCsv)
        }
    }

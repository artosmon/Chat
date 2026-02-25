val marker = "load_date"
val e = expectedCsv.indexOf(marker)
val a = actualCsv.indexOf(marker)
println("expected char after load_date: " + expectedCsv.getOrNull(e + marker.length)?.code)
println("actual   char after load_date: " + actualCsv.getOrNull(a + marker.length)?.code)

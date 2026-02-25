println("expected length=${expectedCsv.length}, actual length=${actualCsv.length}")
println("expected first 120: " + expectedCsv.take(120).replace("\n", "\\n").replace("\r", "\\r").replace("\t", "\\t"))
println("actual   first 120: " + actualCsv.take(120).replace("\n", "\\n").replace("\r", "\\r").replace("\t", "\\t"))

val expIdx = expectedCsv.indexOf('\n')
val actIdx = actualCsv.indexOf('\n')
println("expected first \\n at index=$expIdx")
println("actual   first \\n at index=$actIdx")

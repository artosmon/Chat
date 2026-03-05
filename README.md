@Value
@Builder
@AllArgsConstructor
public class AssessmentReport {
    DocumentKey fileId;
    String fileName;
}

/**
 * Object, identifying saved with content manager document.
 * Internal representation is json serialized object(bucket, path and version attributes)
 * in compact form (omitting property names, with values in array - ("bucket","my/path/to/doc/doc.pdf","123kj123kj12")
 */
public interface DocumentKey {
    String asString();
}

Cannot construct instance of `ru.sberbank.uvz3.contentmanager.DocumentKey` (no Creators, like default constructor, exist): abstract types either need to be mapped to concrete types, have custom deserializer, or contain additional type information
 at [Source: REDACTED (`StreamReadFeature.INCLUDE_SOURCE_IN_LOCATION` disabled); line: 1, column: 12] (through reference chain: java.util.ArrayList[0]->ru.sberbank.uvz3.pledges.facade.pledges.rest.model.AssessmentReport["fileId"])
com.fasterxml.jackson.databind.exc.InvalidDefinitionException: Cannot construct instance of `ru.sberbank.uvz3.contentmanager.DocumentKey` (no Creators, like default constructor, exist): abstract types either need to be mapped to concrete types, have custom deserializer, or contain additional type information
 at [Source: REDACTED (`StreamReadFeature.INCLUDE_SOURCE_IN_LOCATION` disabled); line: 1, column: 12] (through reference chain: java.util.ArrayList[0]->ru.sberbank.uvz3.pledges.facade.pledges.rest.model.AssessmentReport["fileId"])
	at app//com.fasterxml.jackson.databind.exc.InvalidDefinitionException.from(InvalidDefinitionException.java:67)

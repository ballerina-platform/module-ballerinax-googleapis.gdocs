_Author_: Somsole Sai Vamshi Krishna \
_Created_: 03-11-2024 \
_Updated_: 03-11-2024 \
_Edition_: Swan Lake

# Sanitation for OpenAPI specification

This records the sanitization done on top of the OAS from APIs guru. Google uses Google discovery format to expose API details. APIs guru uses a conversion tool to change the discovery documentation to OAS. These sanitation's are done for improving usability and as workaround for known limitations in language side.

[//]: # "TODO: Add sanitation details"

1. Wrapping $ref into allOf - In OpenAPI 2.0 and 3.0.x versions, $ref works by replacing itself and all of its sibling elements with the definition it is pointing at. So the workaround was to wrap $ref into allOf. [Stackoverflow Reference](https://stackoverflow.com/questions/33629750/swagger-schema-properties-ignored-when-using-ref-why)
2. Fix missing single backtick in sectionBreakLocation property description.
3. Add missing description for Request Body of POST /v1/documents API and POST /v1/documents/{documentId}:batchUpdate API

## OpenAPI cli command

The following command was used to generate the Ballerina client from the OpenAPI specification. The command should be executed from the repository root directory.

```bash
$ bal openapi -i docs/spec/openapi.yaml --mode client --license docs/license.txt -o ballerina
```

Note: The license year is hardcoded to 2024, change if necessary.

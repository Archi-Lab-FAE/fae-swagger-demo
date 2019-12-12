# FAE demo project for Swagger with Spring Boot

## Define your API specification

Create your [OpenAPI Specification](https://swagger.io/specification/) in a file
named `openapi.yaml`. An example specification is included in this repository.
It was taken from the [Swagger Editor](https://editor.swagger.io/) example and
converted to OpenAPI 3.0.0 using
[Mermade Swagger 2.0 to OpenAPI 3.0.0 converter](https://mermade.org.uk/openapi-converter).

Open the [Swagger Editor](https://editor.swagger.io/) and import your
`openapi.yaml` file. Then you can edit your OpenAPI specification or view the
generated Swagger UI to explore your API documentation.

It is also possible to generate client or server stubs for multiple languages or
frameworks.

## Generate Spring Boot server stub

Hit the "Generate Server" button and choose "spring". A Zip file containing a
Spring Boot server stub will be downloaded. Extract the Zip file and run the
application:

```bash
unzip ./spring-server-generated.zip -d spring-server-generated
cd spring-server-generated
mvn clean spring-boot:run
```

## View the generated Swagger UI or use the API

By default the application serves the API at server port 8080 and context path
"/v2". You can view the generated Swagger UI at http://localhost:8080/v2 or the
API Docs as JSON at http://localhost:8080/v2/api-docs. The generated API can be
used as well, e.g.:

```bash
curl --verbose --header "Content-Type: application/json" --data @./example-pet.json http://localhost:8080/v2/pet
```

Everything works fine if calls to the API endpoints return HTTP status code 501
(not implemented) and no body, since this is what all generated method stubs
return by default. You can now start implementing your API endpoints by
overriding the methods of the generated Spring controllers and interfaces.

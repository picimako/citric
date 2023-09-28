# Citric Changelog

## 1.0.0

### Added
- **Test frameworks**: Added Citrus specific test frameworks, so that, for instance, IntelliJ can generate Citrus specific test methods in JUnit and TestNG test classes.
- **Test frameworks**: Added an inspection to report test classes that contain at least one `@CitrusTest` or `@CitrusTestSource` annotated method,
  but are not recognized as either Citrus JUnit or Citrus TestNG test classes.
- **Test frameworks**: Added an inspection to report Citrus test classes without `@CitrusTest` and `@CitrusTestSource` annotated methods.
- **Test frameworks**: Added inspection to report incorrect usages of the TestNG specific `@CitrusParameters` annotation.
- **Test frameworks**: Added an intention action to generate the `@CitrusParameters` annotation on a Citrus TestNG test method, based on the test methods' parameter names.
- **Test frameworks**: Parameter names in `@CitrusParameters` are highlighted when the corresponding same-index test method parameter is in focus by the caret.
- **Test frameworks**: Added an inspection to report the combined usage of `@ExtendWith(CitrusSpringExtension.class)` and `@ExtendWith(SpringExtension.class)`. They can be replaced with `@CitrusSpringSupport`.
- **Spring**: Added a line marker for some Spring `@Bean` definition methods that override default Citrus Spring beans.
- **Spring**: Added the **Override Citrus Spring Bean...** action in the editor Generate menu, so that default Citrus specific beans can be overridden in a simpler way.
- **Spring**: Added the **Generate Citrus Endpoint Spring Bean...** action in the editor Generate menu, so that it generates a `@Bean` method for the selected `Endpoint` type.
- **Citrus registry**: Added an inspection to report non-public and void `@BindToRegistry` annotated methods, and `@BindToRegistry` fields without initializers.
- **Citrus registry**: Added intention actions to convert `@BindToRegistry` annotated fields to their corresponding method forms, and vice versa.
- **Citrus registry**: Added an intention action to extract `CitrusContext.bind()` calls to `@BindToRegistry` fields and methods.
- **Resource injection**: Added an inspection to report injected `@CitrusTest` test method parameters when they are not annotated with `@CitrusResource`.
- **Citrus configuration**: Added code completion for Citrus system properties, and values of some of them, in the `citrus-application.properties` file.
- **Citrus configuration**: Added a custom icon for the `citrus-application.properties` file in the IDE Project View.
- **Test variables**: Added code folding for `variable(<name>, <value>)` test variable creation calls to fold them as Java-style `var <name> = <value>` statements.
- **SQL**: Added code completion for SQL transaction isolation levels in the argument of `sql()/query().transactionIsolationLevel(...)`.
- **Test actions**: Added inspection to report `InputAction.Builder#answers()` calls with no argument specified.
- **Test actions**: Added class references to `JavaAction.Builder#java(String)` and `JavaAction.Builder#className(String)`.
- **Test actions**: Added XML language injection to `TransformAction.Builder.source(String)` and `TransformAction.Builder.xslt(String)`.
- **Test actions**: Added Groovy language injection to `ExecuteSQLQueryAction.Builder.groovy(String)`, `ExecuteSQLQueryAction.Builder.validateScript(String, String)`,
  `GroovyAction.Builder.groovy(String)` and `GroovyAction.Builder.script(String)`.
- **Test actions**: Added class references of `Throwable` classes to `Assert.Builder#exception(String)`.
- **Test actions**: Added inspection to report non-Throwable classes specified in `Assert.Builder#exception(String)`.
- **Message validation**: Added XPath language injection for `XpathMessageValidationContext.Builder#expression(String, String)` and `XmlMessageValidationContext.XmlValidationContextBuilder#ignore(String)`.
- **Messaging**: Added code completion for `MessageType` values when sending and receiving messages.
- **Messaging**: Added code completion for JMS and Kafka specific header names in `MessageBuilderSupport.header(String, Object)` when sending and receiving messages. If the concrete Endpoint
  type can be evaluated from the `send()` or `receive()` action call, only the headers specific to that type of messaging are completed.
- **Messaging**: Added code completion for JMS and Kafka specific header names in `Message.setHeader()`, `Message.getHeader()` and `Message.removeHeader()` calls.
- **Messaging**: Added inspection to report and replace JMS and Kafka specific header names with their respective `JmsMessageHeaders` and `KafkaMessageHeaders` constants.
- **Messaging**: Added code completion for content types in HTTP related `contentType()` and `accept()` method call arguments.
- **Citrus 4.x**: Added support for the new package structure introduced in Citrus 4.0.0.
- **Containers**: Added code completion of HTTP method values for `WaitHttpConditionBuilder#method()`.
- **Containers**: Added code folding for `conditional().when().actions()`, `iterate()...actions()` and `sequential().actions()` call chains to collapse them into Java-style code.
- **Containers**: Added code folding for `HamcrestConditionExpression.assertThat()` calls to collapse them into the argument list of `assertThat()`.
- **Functions**: Added simple annotator/syntax highlighting for Citrus function expressions.
- **Validation**: Added simple annotator/syntax highlighting for Citrus validation matchers.
- **Validation**: Added Groovy language injection to `ScriptValidationContext.Builder.script()`.
- **Validation**: Added code completion of `XsdSchema`-type Spring beans in `XmlValidationContextBuilder.schema(String)`
  and `XsdSchemaRepository`-type Spring beans in `XmlValidationContextBuilder.schemaRepository(String)`.
- **Validation**: Added code completion of `SimpleJsonSchema`-type Spring beans in `JsonMessageValidationContext.Builder.schema(String)`
  and `JsonSchemaRepository`-type Spring beans in `JsonMessageValidationContext.Builder.schemaRepository(String)`.
- **Endpoints**: Added inspections to validate `JmsEndpointBuilder` call chains: auto-start requires pub-sub-domain to be enabled,
  durable subscription requires auto-start to be enabled, durable subscriber name takes effect only when durable subscription is enabled.
- **Endpoints**: Added inspections to validate `KafkaEndpointBuilder` call chains: offsetReset must be one of earliest, latest or none. Partition must be a non-negative value.
- **Endpoints**: Added code completion of `Endpoint` type Spring beans in method arguments that accept endpoint URIs, like `send()`, `receive()`, `http().client()` and more.
- **Endpoints**: Added code completion of Kafka offset reset strategies in `KafkaEndpointBuilder.offsetReset()`.
- **Other**: Added inspection to report missing action and container builder calls that would otherwise fail the test execution due to unset properties.
- **Other**: Added reporting for default method argument values with respective quick fixes to remove those redundant calls.
- **Other**: Added various live templates to insert actions and containers.

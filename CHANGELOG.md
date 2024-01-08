# Citric Changelog

## 1.0.5

### Added
- Added an inspection to report JUnit 5 `@ExtendWith(CitrusExtension.class)` annotations, and provide a quick fix to replace them with `@CitrusSupport`.
- [13](https://github.com/picimako/citric/issues/13): Added code completion in the `citrus-application.properties` file for the `citrus.file.path.charset.parameter` property,
  and added completion item descriptions for the properties that haven't had one.
- [14](https://github.com/picimako/citric/issues/14): Added code completion of Citrus functions in Java String literals when completion is invoked at a caret position directly preceded by the `citrus:` function library prefix.
- [15](https://github.com/picimako/citric/issues/15): Added code completion of boolean values for the `citrus.message.pretty.print` and `citrus.logger.modifier` properties in the `citrus-application.properties` file.
- [15](https://github.com/picimako/citric/issues/15): Added regexp language injection into the values of `citrus.*.file.name.pattern` properties.
- [16](https://github.com/picimako/citric/issues/16): Added code completion of Citrus validation matchers in Java String literals when completion is invoked at a caret position preceded and succeeded by an `@` symbol.

### Changed
- Limited the examination of the combination of `SpringExtension.class` and `CitrusSpringExtension.class` in JUnit 5 `@ExtendWith` annotations to this exact order,
  since extensions are executed in the order of their declaration.
- Moved the plugin settings under the *Language & Frameworks* settings page.

### Fixed
- The `citrus.logger.modifier` property in the `citrus-application.properties` file is now code completed with its proper name.
- Modified the Test Method Generation section title in the plugin settings to a clearer one.

## 1.0.4

### Added
- The plugin now works with the Citrus Framework 4.0.0 stable release.
- [8](https://github.com/picimako/citric/issues/8) - **Quarkus**: `@QuarkusTest` and `@CitrusSupport` annotated test classes are now recognized as Citrus Quarkus test classes.
- [8](https://github.com/picimako/citric/issues/8) - **Quarkus**: Added an inspection to validate various aspects of Citrus Quarkus test classes and annotations.
- [6](https://github.com/picimako/citric/issues/6) - **Apache Camel**: Added Spring bean generation for `CamelEndpoint` and `CamelSyncEndpoint`.
- [6](https://github.com/picimako/citric/issues/6) - **Apache Camel**: Added default argument value reporting for the methods of `CamelSyncEndpointBuilder`.
- [6](https://github.com/picimako/citric/issues/6) - **Apache Camel**: Added code completion of headers from `CamelMessageHeaders`, as well as *CamelCorrelationId*, *CamelToEndpoint* and *CamelExceptionCaught*.
- [6](https://github.com/picimako/citric/issues/6) - **Apache Camel**: Added Spring bean code completion of `org.apache.camel.CamelContext` to the `camelContext` attribute of the `@CamelEndpointConfig`
  and `@CamelSyncEndpointConfig` annotations.
- [6](https://github.com/picimako/citric/issues/6) - **Apache Camel**: Added Spring bean code completion of `MessageConverter` to the `messageConverter` attribute of the `@CamelEndpointConfig`
  and `@CamelSyncEndpointConfig` annotations.
- [9](https://github.com/picimako/citric/issues/9) - **Resource injection**: New inspection to report various issues with class fields related to Citrus-injected resources.
- [10](https://github.com/picimako/citric/issues/10) - **Endpoints**: New inspection to report various issues with the following endpoint config annotation configurations:
  `@JmsEndpointConfig`, `@JmsSyncEndpointConfig`, `@KafkaEndpointConfig`, `@HttpClientConfig`, `@HttpServerConfig`, `@WebServiceClientConfig`
- [11](https://github.com/picimako/citric/issues/11) - **@CitrusTestFactory**: Added an inspection to validate `@CitrusTestFactory` annotated test methods from various aspects.
- [11](https://github.com/picimako/citric/issues/11) - **@CitrusTestFactory**: Added an action into the editor Generate menu to generate `@CitrusTestFactory` methods in Citrus JUnit 5 test classes.

### Fixed
- Fixed a NullPointerException regarding classpath and file system resource folding.

### Changed
- Did some optimization regarding message header values.

## 1.0.3

### Added
- [5](https://github.com/picimako/citric/issues/5): Added a line marker for `@CitrusTestSource` annotated test methods.
  It populates a popup menu with actions to navigate to test files and packages referenced by the annotation.
- [7](https://github.com/picimako/citric/issues/5): Added an inspection that analyses the configuration of `@CitrusTestSource` annotations,
  and reports various issues and improvement options on them.

### Fixed
- Fixed a NullPointerException regarding the `@CitrusTestSource` method generation action.

## 1.0.2

### Added
- [3](https://github.com/picimako/citric/issues/3): Introduced the Citric plugin settings page, and added an option to enable/disable
  the **@CitrusTestSource Method** action in the **Generate** editor menu.
- [3](https://github.com/picimako/citric/issues/3): Added plugin settings to configure the list of test DSLs to be code completed in the `type`
  attribute of a `@CitrusTestSource` test method.
- [4](https://github.com/picimako/citric/issues/4): Added line markers for various methods accepting resource paths. The line markers recognize classpath
  resource paths and open the referenced files in a new editor tab.
- Added code folding for `new ClassPathResource(<path>)` instantiation calls to display them as a shorter `"classpath:<path>"` string,
  as well as `new FileSystemResource(<path>)` calls to `"file:<path>"`.
- Added JavaScript language injection into `SeleniumActionBuilder#javascript` and `JavaScriptAction.Builder#script`.

## 1.0.1

### Added
- [1](https://github.com/picimako/citric/issues/1) - **Spring**: Added generation of `WebServiceClient` and `WebServiceServer` Spring beans.
- [1](https://github.com/picimako/citric/issues/1): Added Spring bean completion of `WebServiceClient` beans to `SoapActionBuilder#client` and `AssertSoapFault.Builder#endpoint`,
  `WebServiceServer` beans to `SoapActionBuilder#server` and `AssertSoapFault.Builder#endpoint`, `SoapFaultValidator` beans to `AssertSoapFault.Builder#validator`,
  `SoapAttachmentValidator` beans to `ReceiveSoapMessageAction.SoapMessageBuilderSupport#attachmentValidatorName`.
- [1](https://github.com/picimako/citric/issues/1) - **Endpoints**: Added code completion of `SoapMessageFactory` Spring beans in `WebServiceServerBuilder.messageFactory()`.
- [1](https://github.com/picimako/citric/issues/1) - **Messaging**: Added code completion and reporting (for replacement with utility class constant) of
  message header values from `HttpMessageHeaders`, `SoapMessageHeaders` and `WsAddressingMessageHeaders`.
- [1](https://github.com/picimako/citric/issues/1) - **Endpoints**: Added default argument value reporting for methods of `WebServiceClientBuilder` and `WebServiceServerBuilder`.
- [1](https://github.com/picimako/citric/issues/1): Added Content-Type code completion to `ReceiveSoapMessageAction.SoapMessageBuilderSupport#attachment`, `SoapAttachment#setContentType`
  from `HttpMessageHeaders`, `SoapMessageHeaders` and `WsAddressingMessageHeaders` classes.
- [1](https://github.com/picimako/citric/issues/1): Added XML language injection to `AssertSoapFault.Builder#faultDetail`.
- [1](https://github.com/picimako/citric/issues/1): Added an inspection to report invalid SOAP attachment encoding types in `SoapAttachment#setEncodingType`.
- [2](https://github.com/picimako/citric/issues/2): Added an action to the **Generate** editor menu to generate `@CitrusTestSource` test methods, similar to how the generation of test, setup and teardown methods work.

### Changed
- Renamed some of the client and server specific live template variables to simplify long-term maintenance.
- **Endpoints**: From now on, endpoint Spring bean completion for `HttpActionBuilder#client` and `HttpActionBuilder#server` methods suggest only `HttpClient` and `HttpServer` type endpoints, respectively.

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

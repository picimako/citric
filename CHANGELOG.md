# Citric Changelog

## 1.0.18

### Added
- [50](https://github.com/picimako/citric/issues/50): Added Groovy language injection in the `actions.sql.validate.script.value` property in the YAML DSL.
- [50](https://github.com/picimako/citric/issues/50): Added SQL language injection into
  - `AbstractDatabaseConnectingTestAction.Builder.statement()` calls in the Java and Groovy DSLs,
  - the `sql.statements.statement` and `sql.statement` tags in the XML and Spring XML DSLs, and
  - the `actions.sql.statements.statement` and `actions.plsql.statements.statement` properties in the YAML DSL.
- [50](https://github.com/picimako/citric/issues/50): Added `DataSource` bean completion in the `sql@datasource` attribute in the XML and Spring XML DSLs.
- [50](https://github.com/picimako/citric/issues/50): Added `TransactionManager` bean completion in the `sql.transaction@manager` attribute in the XML,
  and in the `sql@transaction-manager` attribute in the Spring XML DSLs.
- [50](https://github.com/picimako/citric/issues/50): Added completion of SQL `SELECT` statement table column names in
  - `ExecuteSQLQueryAction.Builder.validate()` and `ExecuteSQLQueryAction.Builder.extract()`
    based on `statement()` and `sqlResource()` calls in same call chains, in the Java and Groovy DSLs.
  - the `sql.validate@column` and `sql.extract@column` attributes based on related `statement` and `resource` tags in the XML DSLs.
  - the `sql.validate.column` and `sql.extract.column` properties based on related `statement` and `file` properties in the YAML DSL.
- Added Citrus resource line markers for the arguments of `create()`, `fromClassPath()` and `fromFileSystem()` of `org.citrusframework.spi.Resources`
  in the Java and Groovy DSLs.

### Changed
- Improved the Groovy expression evaluation logic to include binary expressions like `"this is " + "concatenated string"`.

### Fixed
- Fixed a `NullPointerException` that occurred during folding XML closing tags.

## 1.0.17

### Added
- Added JSON language injection into the `message.body.data` XML tag.

### Changed
- Supported IDE range is now 2024.1 - 2024.3.*
- Added the supported Citrus DSL names to the titles of code folding options in the IDE settings.

### Fixed
- Code completions and inspections that require looking up Citrus classes in a project, can now find those classes
  also when the project is Citrus Framework itself.

## 1.0.16

### Added
- [54](https://github.com/picimako/citric/issues/54): Added support for dash-separated YAML property names for YAML DSL specific features:
  resource path line markers, Spring bean code completion and HTTP method code completion.
- [54](https://github.com/picimako/citric/issues/54): Added code completion of `MessageType` constant values in the YAML DSL.
- [54](https://github.com/picimako/citric/issues/54): Added an inspection to validate `MessageType` constant values in a case-insensitive way, in the YAML DSL.
- [55](https://github.com/picimako/citric/issues/55): Added code folding of the closing tag parts of XML tags in Citrus XML and Spring XML test files.
- [53](https://github.com/picimako/citric/issues/53): Added code completion of content types in `content-type` XML attributes, as well as other header `value` attributes.
- [46](https://github.com/picimako/citric/issues/46): Added several different language injections in XML tags and attributes in the XML DSLs.

### Changed
- [54](https://github.com/picimako/citric/issues/54): Updated the YAML DSL schema for example to lift some of the restrictions on property names and types,
  so that both camel-case and dash-separated names are permitted.

### Fixed
- [54](https://github.com/picimako/citric/issues/54): Fixed the YAML schema of SOAP fault objects.

## 1.0.15

### Added
- Added a couple more XML attributes for which resource file line markers can be displayed: `message/resource@file`, `transform/xslt@file`, `message/body/resource@file`, `ant@build-file`.
- Added code folding for the Camel `remove-routes`, `start-routes` and `stop-routes` XML tags in the non-Spring XML DSL.
- [52](https://github.com/picimako/citric/issues/52): Added code folding for the Spring `<meta-info>` tag, the WebSocket `server.endpoints` tag,
  various Selenium action tags, and the Kubernetes `validate.element` tag.

### Fixed
- Fixed an `ArrayIndexOutOfBoundsException` that occurred during code folding of certain XML tags.
- Fixed some of the XML tag folders to retrieve the proper local names of tags when determining the eligibility for folding.

## 1.0.14

### Added
- [47](https://github.com/picimako/citric/issues/47): Added many more Spring XML attributes to the list of locations
  where a line marker is displayed for Citrus resource paths.
- Citric now works in the actual [Citrus GitHub project](https://github.com/citrusframework/citrus) via enabling it in
  the Citric plugin settings with a newly introduced option.
- Added `@CitrusSpringXmlTestFactory` to be recognized as Citrus JUnit 5 test factory annotations.
- [40](https://github.com/picimako/citric/issues/40): Added code folding for various tags in the Citrus XML and Spring XML DSLs.

### Changed
- Citrus JUnit 5 classes are now recognized also when the `@ExtendWith` annotation is passed in multiple extension types.

### Fixed
- Fixed an exception that occurred when trying to get the last element of an empty collection.
- Added missing description to an inspection.
- Fixed a `StringIndexOutOfBoundsException` during annotation Citrus validation matchers.
- Fixed an exception that occurred because of unchecked file absence.
- Handled an `IndexNotReadyException` when checking Citrus TestNG test classes.
- Fixed a false positive inspection report on missing conditions in `waitFor()` call chains.
- Fixed a `NullPointerException` that occurred during registering Citrus resource file line markers.

## 1.0.13

### Added
- [41](https://github.com/picimako/citric/issues/41): Added support for the current Citric feature set in the Citrus XML and Spring XML DSLs:
  for example: code completions for content-types, message headers, SQL transaction isolation levels, also line markers for attributes
  accepting Citrus resource paths, and more.

### Changed
- Updated the Spring bean completions' icons to distinguish them between Java and XML bean definitions.

### Fixed
- Fixed an exception regarding duplicate registration attempt of Run and Debug test source files line marker actions.

## 1.0.12

### Added
- [39](https://github.com/picimako/citric/issues/39): Added code folding for `iterate()....().actions()` call chains in Groovy test files to collapse them into Groovy-style code.
- [39](https://github.com/picimako/citric/issues/39): Added Groovy DSL support for eligible inspections, line markers and references.
- [44](https://github.com/picimako/citric/issues/44): Disabled the execution of many features (inspections, line markers, etc.) in projects that don't use Citrus.
- [32](https://github.com/picimako/citric/issues/32): Added an action into the editor Generate menu to generate `@CitrusSpringXmlTestFactory` methods in Citrus JUnit 5 test classes.
- [32](https://github.com/picimako/citric/issues/32): Added an inspection to validate `@CitrusSpringXmlTestFactory` annotated test methods from various aspects.
- [32](https://github.com/picimako/citric/issues/32): Added inspections to validate the combined usage of `@CitrusSpringXmlTestFactory` and non-Spring-XML test creation with `CitrusTestFactorySupport`,
  as well as to report various issues on calls on `CitrusTestFactorySupport`.
- [32](https://github.com/picimako/citric/issues/32): Added a line marker to calls on `CitrusTestFactorySupport`, so that users can navigate to the test source files and directories
  referenced by those calls.

### Changed
- Improved Groovy expression evaluation logic, so that variable values are now also evaluated e.g. during container folding.

### Fixed
- Fixed a couple of 'Slow operations are prohibited on EDT' exceptions.

## 1.0.11

### Added
- [39](https://github.com/picimako/citric/issues/39): Added HTTP request method code completion for `WaitHttpConditionBuilder#method()` in Groovy test files.
- [39](https://github.com/picimako/citric/issues/39): Added code completion of Kafka offset reset strategies in `KafkaEndpointBuilder.offsetReset()` in Groovy test files.
- [39](https://github.com/picimako/citric/issues/39): Added code completion of `SimpleJsonSchema`-type Spring beans in `JsonMessageValidationContext.Builder.schema(String)`
  and `JsonSchemaRepository`-type Spring beans in `JsonMessageValidationContext.Builder.schemaRepository(String)` in Groovy test files.
- [39](https://github.com/picimako/citric/issues/39): Added code completion of `XsdSchema`-type Spring beans in `XmlValidationContextBuilder.schema(String)`
  and `XsdSchemaRepository`-type Spring beans in `XmlValidationContextBuilder.schemaRepository(String)` in Groovy test files.
- [39](https://github.com/picimako/citric/issues/39): Added code completion for `MessageType` values when sending and receiving messages in Groovy test files.
- [39](https://github.com/picimako/citric/issues/39): Added code completion for JMS, Kafka, etc. specific header names in `Message.setHeader()`, `Message.getHeader()` and `Message.removeHeader()` calls,
  as well as in `MessageBuilderSupport.header(String, Object)` when sending and receiving messages in Groovy test files.
- [39](https://github.com/picimako/citric/issues/39): Added code completion for SQL transaction isolation levels in the argument of `sql()/query().transactionIsolationLevel(...)` in Groovy test files.
- [39](https://github.com/picimako/citric/issues/39): Added code completion of many different Spring bean types in Groovy test files.
- [39](https://github.com/picimako/citric/issues/39): Added code folding for `conditional().when().actions()` and `sequential().actions()` call chains in Groovy test files to collapse them into Groovy-style code.
- [39](https://github.com/picimako/citric/issues/39): Added code folding for `HamcrestConditionExpression.assertThat()` calls to collapse them into the argument list of `assertThat()` in Groovy test files.

### Changed
- Supported IDE range is now 2023.3 - 2024.2-EAP.
- Disabled custom test source file icons in IJ-2023.3.* due to IntelliJ Platform changes no suitable alternative to display. They are enabled in IJ-2024.1 and up.
- Restricted the 'Wait for http method' code completion in YAML files to actual Citrus YAML test files.

### Fixed
- Eliminated *"Slow operations are prohibited on EDT."* errors in a couple of places, so they won't spam the logs.

## 1.0.10

### Fixed
- Fixed an exception regarding an HTTP method code completion in YAML test files.
- Fixed a syntax issue in the YAML DSL schema that may have prevented proper parsing.
- Fixed the code completion of root-level YAML DSL schema keys.

## 1.0.9

### Added
- [36](https://github.com/picimako/citric/issues/36): Added support for `file:` and `jar:` resources when looking up resources referenced by te `@CitrusTestSource`, as well as
  during test source file execution and navigation to matching `@CitrusTestSource`.
- [36](https://github.com/picimako/citric/issues/36): Added support for `file:` and `jar:` resources when showing line markers for methods accepting Citrus resource paths.
- [42](https://github.com/picimako/citric/issues/42): Added a line marker in YAML test files to properties that accept
  `classpath:`, `file:`, `jar:` and `http:` resource paths, so that users can navigate to them.
- [42](https://github.com/picimako/citric/issues/42): Added HTTP request method code completion for the `actions.waitFor.http.method` property value in YAML test files.
- [42](https://github.com/picimako/citric/issues/42): Added code completion for various Spring bean names in YAML test files.
- [42](https://github.com/picimako/citric/issues/42): Added inspection to report non-Throwable classes specified in the `actions.assert.exception` property value in YAML test files.
- [42](https://github.com/picimako/citric/issues/42): Added class references of `Throwable` classes in the `actions.assert.exception` property value in YAML test files.

### Changed
- Directory paths are now filtered out from line markers and the test source file recognition when specified in the `sources` attribute
  of the `@CitrusTestSource` annotation.
- Citrus 4.x YAML DSL schema is extended with several property descriptions, including examples and default values for code completion, as well as possible property
  values for automatic validation.
- Added the Citrus resource path line markers to a couple more Citrus Java methods.
- Added code completion for a couple more types of Spring beans in the Java DSL.

### Fixed
- Custom test source file icons are now displayed with a lot less false positive matches.
- Fixed the YAML DSL schema for some SOAP message related configurations.
- All types of non-`Throwable` values are now reported in the argument list of `Assert.Builder#exception()`.

## 1.0.8

### Added
- [28](https://github.com/picimako/citric/issues/28): Added the **Run Test** and **Debug Test** actions to the Project View context menu
  of Citrus Yaml test files.
- [33](https://github.com/picimako/citric/issues/33): Extended the Run/Debug Citrus YAML test line marker and Project View actions, so that users
  can select an arbitrary `@CitrusTestSource` annotated method to execute, if the action would fail to recognize test methods as ones covering the particular YAML file.
- [34](https://github.com/picimako/citric/issues/34): Added Run/Debug actions for Citrus Groovy test files inside a line marker
  and in the Project View context menu.
- [35](https://github.com/picimako/citric/issues/35): Added an action that can navigate to matching JUnit/TestNG test methods from Citrus Groovy test files.
- [37](https://github.com/picimako/citric/issues/37): Added the **Run Test** and **Debug Test** actions inside a line marker and the Project View context menu
  for Citrus XML and Citrus Spring XML test files.
- [37](https://github.com/picimako/citric/issues/37): Added actions that can navigate to matching JUnit/TestNG test methods from Citrus XML and Citrus Spring XML test files.

## 1.0.7

### Changed
- Supported IDE range is now 2023.2.1 - 2024.1.

### Added
- [29](https://github.com/picimako/citric/issues/29): Added custom, test specific icons to XML, YAML and Groovy Citrus test source files.
- [30](https://github.com/picimako/citric/issues/30): Added respective custom icons on editor tabs and other places for the citrus-application.properties,
  as well as to XML, YAML and Groovy Citrus test source files.
- [26](https://github.com/picimako/citric/issues/26): Added a line marker in Citrus YAML test source files to be able to
  run and debug a `@CitrusTestSource` annotated JUnit or TestNG test method that covers the YAML file the action is invoked from.
- Added titled separators for the line marker actions displayed for each `@CitrusTestSource` annotated method. They show which parts of the
  annotation configuration the actions come from.
- [25](https://github.com/picimako/citric/issues/25): Added an action that can navigate to, or present a list of matching JUnit/TestNG test methods to navigate to,
  from Citrus YAML test files. The action may be invoked with Ctrl+Shift+T, just like navigation from production classes to
  their corresponding test classes works in Java projects.
- `@CitrusTestFactory` and `@CitrusTestSource` test methods can now be generated inside `@Nested` JUnit 5 test classes as well.
- [31](https://github.com/picimako/citric/issues/31) - **Citrus 4.2.0**: Added code completion for the new, sharding specific, Citrus system properties.
- [31](https://github.com/picimako/citric/issues/31) - **Citrus 4.2.0**: Added an inspection to report issues with sharding related configuration
  in the `citrus-application.properties` file.

### Fixed
- Fixed an exception during project initialization.
- Fixed an exception that occurred during previewing the quick fix results for the deletion of the `@CitrusTestSource` annotation's name attribute
  when it matches the test method name.
- Fixed some exceptions that occurred during retrieving data for the line marker for `@CitrusTestSource` annotated test methods.
- Fixed the potential blinking or even disappearance of line markers on `@CitrusTestSource` annotated test methods.
- Fixed an issue that `@Nested` JUnit 5 classes inside Citrus JUnit 5 parent test classes were falsely reported as not valid Citrus test classes.

## 1.0.6

### Changed
- Supported IDE range is now 2023.2 - 2024.1-EAP.
- [18](https://github.com/picimako/citric/issues/18): Added YAML schema for Citrus YAML test case files. Schema is available for Citrus v3.4.0 and 4.x for files ending with `(test|it)\.(yaml|yml)`.
- [19](https://github.com/picimako/citric/issues/19): Added code completion of Citrus functions and validation matchers to XML, JSON, YAML and Groovy files.
- Improved code completion of Citrus functions and validation matchers: the caret is no longer moved inside the function/matcher call parentheses
  for parameterless functions/matchers to provide a bit smoother coding experience.
- [20](https://github.com/picimako/citric/issues/20): Syntax highlighting is now properly applied for nested Citrus functions and nested validation matchers,
  as well as string literal, boolean, number and other types of function arguments.
- [21](https://github.com/picimako/citric/issues/21): Introduced plugin settings to toggle the syntax highlighting for Citrus functions and validation matchers per language.
- [22](https://github.com/picimako/citric/issues/22): Added `Endpoint` Spring bean completion to `org.citrusframework.camel.dsl.CamelSupport#endpoint(String)`.
- [23](https://github.com/picimako/citric/issues/23): Added Citrus functions and validation matchers syntax highlighting to XML, JSON, YAML and Groovy files.
- [24](https://github.com/picimako/citric/issues/24): Added code completion of many more Citrus property keys and values in `citrus-application.properties` files.

### Fixed
- [20](https://github.com/picimako/citric/issues/20): The `containsIgnoreCase` matcher was missing from the validation matcher syntax highlighting.
- Fixed some exceptions regarding missing `ReadAction` invocations.

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

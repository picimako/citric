# Citric

[![Version](https://img.shields.io/jetbrains/plugin/v/22813-citric.svg)](https://plugins.jetbrains.com/plugin/22813-citric)

Citric is an IntelliJ-based plugin that provides framework integration for the [Citrus](https://citrusframework.org/) framework.

> [!IMPORTANT]
> Citric is no longer in development and sales are suspended.

It offers various tools to generate and validate Citrus related test code in the following areas, among others:
- Citrus specific [JUnit and TestNG test frameworks](https://www.picimako.com/citric/test-frameworks), e.g. for generating Citrus test methods.
- Validation and generation of Citrus test methods and TestNG specific `@CitrusParameters`.
- Code completion of [Endpoint](https://www.picimako.com/citric/endpoints/) Spring beans,
  [XML and JSON schema](https://www.picimako.com/citric/messaging/) Spring beans,
  [properties in `citrus-application.properties`](https://www.picimako.com/citric/citrus-and-spring-configuration/), message headers and more.
- Basic syntax highlighting for [Citrus functions](https://www.picimako.com/citric/citrus-functions/) and [validation matchers](https://www.picimako.com/citric/messaging/).
- [Language injections](https://www.picimako.com/citric/language-injections/) at various locations
- Validation and conversion of [`@BindToRegistry` methods and fields](https://www.picimako.com/citric/citrus-registry-and-resource-injection/)
- Numerous Citrus-specific static code analysis checks
- Code folding of certain [containers](https://www.picimako.com/citric/containers/) and Hamcrest condition expressions for easier comprehension of test code

## Supported IDEs

The list of supported IDEs include all free versions of IntelliJ (Community, Educational, etc.) as well as Ultimate.

## Documentation

The documentation is available on its [dedicated website](http://www.picimako.com/citric/).

## OSS attributions

This project derives some documentation from the [Citrus](https://github.com/citrusframework/citrus/) open source project.
This content is licensed under the Apache License v2.

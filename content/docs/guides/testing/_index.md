---
title: Testing
meta_desc: TODO.
menu:
    userguides:
        identifier: testing
        weight: 7
---

Pulumi uses general-purpose programming languages to define cloud infrastructure. This capability opens up all the doors to **automated testing** of the infrastructure resources.

The software industry has come up with multiple styles of automated testing. Unit testing of individual pieces, integration testing of system components, end-to-end testing of the complete application&mdash;each style has its advantages and challenges.

Pulumi provides a similar choice of testing options for cloud programs. Currently, we identify three types of tests:

- **Unit Tests** are fast in-memory tests that mock all external calls.
- **Tests based on Policy as Code** run resource-level assertions *while* infrastructure is being deployed.
- **Integration Tests** deploy ephemeral infrastructure and run external tests against it.

The following table summarizes the differences between the three approaches:

|                                | Unit Tests  | Policy as Code  | Integration Tests  |
|--------------------------------|-----|------|------|
| Provision real infrastructure  | No  | Yes  | Yes  |
| Require the Pulumi CLI         | No  | Yes  | Yes  |
| Time to execute                | Milliseconds  | Seconds to minutes  | Seconds to minutes  |
| Language                       | Same as Pulumi program  | Node.js or Python  | Any language  |
| Validation target              | Resource inputs  | Resource inputs and outputs | External endpoints |

We encourage you to try all three styles of testing and use the ones that are most suitable for your quality targets, development practices, and application style.

## Unit Testing

If you ever created unit tests for your application code, you can directly transfer your skills to testing Pulumi programs. Unit tests evaluate the behavior of your code in isolation, while all external dependencies are replaced by **test doubles** (mocks).

Unit tests run in memory without any out-of-process calls, which makes them blazingly fast. Therefore, unit tests are suitable for fast feedback loops during development, including **Test-Driven Development** (TDD).

You author the unit tests in the same language as the Pulumi program under test. You are free to use your favorite test and mock frameworks like Mocha for Node.js or NUnit for .NET.

Because there are no real cloud resources created, you can't write a test that would evaluate the behavior of infrastructure. For example, you can't make HTTP requests to endpoints: there's no webserver to serve them.

[Learn more and get started with Unit Testing]({{< relref "./unit" >}}).

## Integration Testing

Integration testing takes the opposite approach: the tests deploy real cloud resources and validate their actual **behavior**.

The flow goes like this:

1. A test invokes the Pulumi command-line interface (CLI) to deploy infrastructure to an ephemeral environment.
2. When deployment succeeds, the test queries stack outputs to retrieve endpoints of the infrastructure: usually, a URL or a public IP address.
3. The test verifies that the infrastructure behaves as expected: for example, it expects a valid HTML document from a health-check endpoint.
4. Upon completion, the infrastructure is destroyed.

The great advantage of integration tests is the ability to test the actual cloud infrastructure and its real properties. However, compared to unit tests, integrations tests take a long time to execute.

Depending on the type of resources and frequency of testing, even short-lived ephemeral environments may incur notable charges from the cloud provider. Be sure to plan accordingly and measure frequently.

[Learn more and get started with Integration Testing]({{< relref "./integration" >}}).

## Testing with Policy as Code

[Policy as Code]({{< relref "../crossguard" >}}) (also known as "CrossGuard") is Pulumi's offering to set guardrails and enforce compliance for cloud resources. In addition to authoring company-wide policies, CrossGuard enables another type of infrastructure testing.

Policy-based tests run inside the Pulumi CLI before and after infrastructure provisioning. In contrast to "black-box" integration testing, policy rules have access to all input and output values of all cloud resources in the stack. As opposed to unit testing, policy rules can evaluate real values returned from the cloud provider instead of test doubles.

Policy-based tests run against an ephemeral cloud environment, so the considerations of speed and cost still apply.

[Learn more and get started with Policy as Code testing]({{< relref "./policy-as-code" >}}).

## Examples

Several complete and runnable tests are available in the [examples repository](https://github.com/pulumi/examples#testing):

Example		| Description |
----- 		| --------- |
[Unit Tests in TypeScript](https://github.com/pulumi/examples/testing-unit-ts)      | Mock-based unit tests in TypeScript.
[Unit Tests in Python](https://github.com/pulumi/examples/testing-unit-python)  | Mock-based unit tests in Python.
[Unit Tests in Go](https://github.com/pulumi/examples/testing-unit-go)      | Mock-based unit tests in Go.
[Unit Tests in C#](https://github.com/pulumi/examples/testing-unit-cs)      | Mock-based unit tests in C#.
[Policy Testing in TypeScript](https://github.com/pulumi/examples/testing-pac-ts)       | Tests based on Policy-as-Code in TypeScript.
[Integration Testing in Go](https://github.com/pulumi/examples/testing-integration)  | Deploy-check-destroy tests in Go.

# Test Jmix 2.1.1 project

This is a test project for Jmix 2.1.1 to demonstrate the failure of the UI test when too many are performed.
Running each test individually works fine, but running all tests at once fails.

We have a big projects with many UI tests and attempting to migrate to Jmix 2.1.1, we found that the UI tests hang
indefinitely after a certain number of tests.

To demonstrate this, I created a new project with the Jmix 2.1.1 archetype and added to the default `UserUiTest` the
annotation `@RepeatedTest(500)` to the default test method.
Usually, it hangs indefinitely around the 134th repetition.

## Steps to reproduce

```shell
./gradlew clean test --tests "UserUiTest"

```

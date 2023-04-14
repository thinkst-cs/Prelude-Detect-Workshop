# Creating Tests

Security tests are production-ready versions of TTPs. Tests have characteristics that encourage scale and safety.

## Learning Objectives

1. Create a test
2. Modify a test
3. Upload a test

## Exercises

### 1. Create a test

Let's create a test that will write a Pneuma agent for Prelude Operator to disk. The purpose of this test is to assess whether EDR or AV on your host will quarantine known malware.

- Using the Prelude CLI, create a new test named `Will your computer quarantine Pneuma?`.
- What is the ID of the test?

### 2. Modify a test

Creating a test is only the first step. You need to modify the test template created in the previous step to make it useful.

Let's download a copy of [Pneuma](https://github.com/VVX7/pneuma-binaries) and modify the test to write the Pneuma agent to disk. This Pneuma binary has not been defanged.

An example of a test that writes a malicious file to disk can be found [here](https://github.com/preludeorg/test/tree/master/tests/74077d3b-6a2f-49fa-903e-99cad6f34cf6).

- Open the test using your preferred IDE.
- Modify the test to write the Pneuma agent to disk.
- Look at the test exit codes in the example test. What do they mean?

### 3. Upload a test

Now that you have created and modified a test, you need to upload it to Detect's compiler service which is called Compute. Compute automatically cross-compiles tests for all supported operating systems.

To upload a modified test, or files that will be embedded in the test such as the Pneuma agent, use the Prelude CLI and specify the test ID and the file to upload.

- Upload the test using the Prelude CLI.
- Upload the Pneuma agent to the Prelude platform using the Prelude CLI.

## Help

### Create a test

```
prelude build create-test <TEST_NAME>
```

### Upload a test

```
prelude build upload -t <TEST_ID> <TEST_FILE>
```

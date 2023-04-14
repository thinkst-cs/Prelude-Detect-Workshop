# Enabling Tests

[Enabling a security test](https://docs.preludesecurity.com/docs/detect-getting-started#enable-tests) makes it available for execution on active probes.

## Learning Objectives

1. List tests
2. View test queue
3. Enable a test

## Exercises

### 1. List tests

Your Prelude account comes with a set of default tests. Use the Prelude CLI to list all tests in your account.

- What is the ID of the test named `Can a base64 encoded script be run`?


### 2. View test queue

Use the Prelude CLI to view the test queue.

- How many tests are in the queue?
- What is name of the test in the queue?

### 3. Enable a test

By default, tests are enabled to run once a day. You can change this by using the `--run_code` flag.

Enable the `Can a base64 encoded script be run?` test and schedule it to run once a day. Add the `DetectWorkshop` tag to this test. Adding a tag to a test limits execution to endpoints with that tag.

- What is the run code for the test?

## Help

### List tests

```
prelude detect tests
```

### View test queue

```
prelude detect queue
```

### Enable a test

```
prelude detect enable-test <ID> --run_code <DAILY|WEEKLY|MONTHLY> --tags <TAG_1,TAG_2>
```

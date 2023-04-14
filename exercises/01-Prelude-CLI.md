 # Prelude CLI

The [Prelude Command Line Interface](https://docs.preludesecurity.com/docs/prelude-cli) (CLI) supplies programmatic access to the full suite of Prelude APIs. It is written in Python and will run on any MacOS or Linux machine with Python installed.

## Learning Objectives

1. Install the Prelude CLI
2. Create a Prelude account
3. View your account information

## Exercises

### 1. Install the Prelude CLI

Create a Python virtual environment and install the [prelude-cli](https://pypi.org/project/prelude-cli/) Python PIP package.

### 2. Create a Prelude account

Create a Prelude account using the Prelude CLI. 

You must use a valid email address for the account handle. A verification email will be sent to your email address to activate your Prelude account.

- What is your Prelude account ID?

### 3. View your account information

View your Prelude account information using the Prelude CLI.

- When does your account expire?

## Help

### Install prelude-cli

#### Configure a Python virtual environment

```
python3 -m venv venv
```

#### Activate the virtual environment

```
source venv/bin/activate
```

#### Install prelude-cli

```
pip3 install prelude-cli
```

#### Confirm the installation

```
prelude --help
```

### Create a Prelude account

```
prelude iam create-account
```

### View your account information

```
prelude iam account
```

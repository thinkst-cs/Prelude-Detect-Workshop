# Deploying Probes



## Learning Objectives

1. Download an ephemeral probe
2. Run an ephemeral probe
3. Optional: Install a persistent probe

## Exercises

### 1. Download an ephemeral probe

[Ephemeral probes](https://docs.preludesecurity.com/docs/ephemeral-probes) are lightweight processes with the smallest footprint possible. They are designed to run without dependencies on any modern version of Linux or MacOS.

#### Linux/MacOS

[Nocturnal](https://github.com/preludeorg/libraries/blob/master/shell/probe/nocturnal.sh) is a lightweight Bash script that runs on any modern version of Linux or MacOS.

- Download [Nocturnal](https://github.com/preludeorg/libraries/blob/master/shell/probe/nocturnal.sh) probe.

#### Windows

[Raindrop](https://github.com/preludeorg/libraries/blob/master/shell/probe/raindrop.ps1) is a lightweight PowerShell script that runs on any modern version of Windows.

- Download [Raindrop](https://github.com/preludeorg/libraries/blob/master/shell/probe/raindrop.ps1) probe. 

### 2. Run an ephemeral probe

Probes are linked to a Prelude account via their endpoint token. An endpoint token is generated when an endpoint is registered.

- Using the endpoint token from the previous exercise, run the probe.

### 3. Optional: Install a persistent probe

[Persistent probes](https://docs.preludesecurity.com/docs/installation-options) install as a service to survive machine reboots, restart if stopped and upgrade automatically.

- Using the Prelude CLI, create a registration user. This will generate a low-privilege authentication token. 
- Use the low-privilege authentication token, along with an account ID, to install a persistent probe.

## Help

### Download an ephemeral probe

#### Linux/MacOS

```
curl https://raw.githubusercontent.com/preludeorg/libraries/master/shell/probe/nocturnal.sh -o nocturnal.sh
```

#### Windows

```
curl https://raw.githubusercontent.com/preludeorg/libraries/master/shell/probe/raindrop.ps1 -o raindrop.ps1
```

### Run an ephemeral probe

#### Linux/MacOS

```
export PRELUDE_TOKEN=<TOKEN>
./nocturnal.sh
```

#### Windows

```
SETX PRELUDE_TOKEN <TOKEN> /M
.\raindrop.ps1
```

### Optional: Install a persistent probe

#### Create a Registration User

This will generate a low-privilege authentication token. Use this, along with an account ID, to install probes.

```
prelude detect create-user registration --permission SERVICE
```

#### Linux

All modern versions of Ubuntu, CentOS and Amazon 2 are supported. Mileage may vary on other distributions, such as RHEL or Debian, as these are not tested regularly. SELinux is not supported.

RPM
```
sudo rpm -Uvh https://api.preludesecurity.com/download/install/detect-1.0.0.rpm
sudo detect-register-endpoint -r <ACCOUNT_ID>/<TOKEN> -t tag1,tag2,tag3
```

Amazon AM2

```
sudo yum install https://api.preludesecurity.com/download/install/detect-1.0.0.rpm
sudo detect-register-endpoint -r <ACCOUNT_ID>/<TOKEN> -t tag1,tag2,tag3
```

Ubuntu

```
curl -sL https://api.preludesecurity.com/download/install/detect-1.0.0.deb -o detect-1.0.0.deb
sudo dpkg -i detect-1.0.0.deb
rm detect-1.0.0.deb
sudo detect-register-endpoint -r <ACCOUNT_ID>/<TOKEN> -t tag1,tag2,tag3
```

#### MacOS

All versions of Intel and ARM are supported.

```
curl -sL https://api.preludesecurity.com/download/install/detect-1.0.0.pkg -o detect-1.0.0.pkg
sudo launchctl setenv REGISTRATION_STRING <ACCOUNT_ID>/<TOKEN> ENDPOINT_TAGS tag1,tag2,tag3
sudo installer -pkg detect-1.0.0.pkg -target /
```

#### Windows

The following versions are supported: Windows 10, Windows 11, Server 2019 and Server 2022.

[Download the MSI](https://api.preludesecurity.com/download/install/detect-1.0.0.msi).

```
msiexec.exe /qn /l*v detect-log.txt /i detect-1.0.0.msi REGISTRATION_STRING="<ACCOUNT_ID>/<TOKEN>" ENDPOINT_TAGS="tag1,tag2,tag3"
```


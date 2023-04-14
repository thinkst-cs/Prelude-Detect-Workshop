# Registering Endpoints

Endpoints are simply hosts running a Prelude probe. A Prelude account is required to [register endpoints](https://docs.preludesecurity.com/docs/detect-getting-started#register-endpoints). 

## Learning Objectives

1. Register an endpoint
2. View endpoint information
3. Delete an endpoint

## Exercises

### 1. Register an endpoint

Registering an endpoint generates a new endpoint token that is used when deploying a probe. 

Register an endpoint using the Prelude CLI. Use your own hostname and your own IP for the serial number. For a tag, use `DetectWorkshop,TLP:WHITE`.

- What is the value of the endpoint token?

### 2. View endpoint information

View endpoint information using the Prelude CLI.

- What is the endpoint ID?

### 3. Delete an endpoint

Create a new endpoint and then delete it using the Prelude CLI.

Register a new endpoint but this time use the hostname `DeleteMe` and your `1234` for the serial number. For a tag, use `DetectWorkshop`.

View the endpoint information and note the endpoint ID of the new endpoint.

Delete the endpoint using the Prelude CLI.

-  What is the endpoint ID of the `DeleteMe` endpoint?
-  After deleting the new endpoint, what is the output of the `prelude detect endpoints` command?


## Help

### Register an endpoint

```
prelude detect create-endpoint -h <HOSTNAME> -s <SERIAL_NUM> -t <TAG_1,TAG_2>
```

### View endpoint information

```
prelude detect endpoints
```

### Delete an endpoint

```
prelude detect delete-endpoint <ENDPOINT_ID>
```

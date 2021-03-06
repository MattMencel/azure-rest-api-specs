# Authorization

> see https://aka.ms/autorest

This is the AutoRest configuration file for Authorization.



---
## Getting Started
To build the SDK for Authorization, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration



### Basic Information
These are the global settings for the Authorization API.

``` yaml
openapi-type: arm
tag: package-2018-01-01-preview
```

## Suppression
``` yaml
directive:
  - suppress: OperationsAPIImplementation
    reason: we do have a operations api as "/providers/Microsoft.Authorization/operations"
    #where:
    #  -   $.paths["/providers/Microsoft.Authorization/operations"]

```

### Tag: package-2015-07

These settings apply only when `--tag=package-2015-07` is specified on the command line.

``` yaml $(tag) == 'package-2015-07'
input-file:
- Microsoft.Authorization/stable/2015-07-01/authorization.json
```

### Tag: package-2017-10-01-preview

These settings apply only when `--tag=package-2017-10-01-preview` is specified on the command line.

``` yaml $(tag) == 'package-2017-10-01-preview'
input-file:
- Microsoft.Authorization/preview/2015-06-01/authorization-ClassicAdminCalls.json
- Microsoft.Authorization/preview/2015-07-01/authorization.json
- Microsoft.Authorization/preview/2017-10-01-preview/authorization-RACalls.json
```

### Tag: package-2018-01-01-preview

These settings apply only when `--tag=package-2018-01-01-preview` is specified on the command line.

``` yaml $(tag) == 'package-2018-01-01-preview'
input-file:
- Microsoft.Authorization/preview/2015-06-01/authorization-ClassicAdminCalls.json
- Microsoft.Authorization/preview/2018-01-01-preview/authorization-RoleBasedCalls.json
```

---
# Code Generation


## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-python
  - repo: azure-libraries-for-java
  - repo: azure-sdk-for-go
  - repo: azure-sdk-for-node
```


## C#

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

``` yaml $(csharp)
csharp:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.Azure.Management.Authorization
  output-folder: $(csharp-sdks-folder)/Authorization/Management.Authorization/Generated
  clear-output-folder: true
```

## Python

These settings apply only when `--python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.
Use `--python-mode=update` if you already have a setup.py and just want to update the code itself.

``` yaml $(python)
python-mode: create
python:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  payload-flattening-threshold: 2
  namespace: azure.mgmt.authorization
  package-name: azure-mgmt-authorization
  package-version: 0.40.0
  clear-output-folder: true
```
``` yaml $(python) && $(python-mode) == 'update'
python:
  no-namespace-folders: true
  output-folder: $(python-sdks-folder)/azure-mgmt-authorization/azure/mgmt/authorization
```
``` yaml $(python) && $(python-mode) == 'create'
python:
  basic-setup-py: true
  output-folder: $(python-sdks-folder)/azure-mgmt-authorization
```

## Go

These settings apply only when `--go` is specified on the command line.

``` yaml $(go)
go:
  license-header: MICROSOFT_APACHE_NO_VERSION
  namespace: authorization
  clear-output-folder: true
```

### Go multi-api

``` yaml $(go) && $(multiapi)
batch:
  - tag: package-2015-07
  - tag: package-2017-10-01-preview
  - tag: package-2018-01-01-preview
```

### Tag: package-2015-07 and go

These settings apply only when `--tag=package-2015-07 --go` is specified on he command line.
Please also specify `--go-sdk-folder=<path to the root directory of your azure-sdk-for-go clone>`.

``` yaml $(tag) == 'package-2015-07' && $(go)
output-folder: $(go-sdk-folder)/services/authorization/mgmt/2015-07-01/authorization
```

### Tag: package-2017-10-01-preview and go

These settings apply only when `--tag=package-2017-10-01-preview --go` is specified on he command line.
Please also specify `--go-sdk-folder=<path to the root directory of your azure-sdk-for-go clone>`.

``` yaml $(tag) == 'package-2017-10-01-preview' && $(go)
output-folder: $(go-sdk-folder)/services/authorization/mgmt/2017-10-01-preview/authorization
```

### Tag: package-2018-01-01-preview and go

These settings apply only when `--tag=package-2018-01-01-preview --go` is specified on he command line.
Please also specify `--go-sdk-folder=<path to the root directory of your azure-sdk-for-go clone>`.

``` yaml $(tag) == 'package-2018-01-01-preview' && $(go)
output-folder: $(go-sdk-folder)/services/authorization/mgmt/2018-01-01-preview/authorization
```

## Java

These settings apply only when `--java` is specified on the command line.
Please also specify `--azure-libraries-for-java-folder=<path to the root directory of your azure-libraries-for-java clone>`.

``` yaml $(java)
java:
  azure-arm: true
  fluent: true
  namespace: com.microsoft.azure.management.authorization
  license-header: MICROSOFT_MIT_NO_CODEGEN
  payload-flattening-threshold: 1
  output-folder: $(azure-libraries-for-java-folder)/azure-mgmt-authorization
```
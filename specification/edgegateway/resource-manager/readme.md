# DataBox

> see https://aka.ms/autorest

This is the AutoRest configuration file for DataBox.



---
## Getting Started
To build the SDK for DataBox, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration



### Basic Information
These are the global settings for the DataBox API.

``` yaml
openapi-type: arm
tag: package-2019-03
```

### Tag: package-2019-03

These settings apply only when `--tag=package-2019-03` is specified on the command line.

``` yaml $(tag) == 'package-2019-03'
input-file:
- Microsoft.DataBoxEdge/stable/2019-03-01/edgegateway.json
```

---
# Code Generation


## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-python
  - repo: azure-sdk-for-js
  - repo: azure-sdk-for-go
  - repo: azure-sdk-for-java
  - repo: azure-sdk-for-ruby
    after_scripts:
      - bundle install && rake arm:regen_all_profiles['azure_mgmt_edgegateway']
```

## C#

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

``` yaml $(csharp)
csharp:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.Azure.Management.EdgeGateway
  payload-flattening-threshold: 2
  output-folder: $(csharp-sdks-folder)/EdgeGateway/Management.EdgeGateway/Generated
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
  namespace: azure.mgmt.edgegateway
  package-name: azure-mgmt-edgegateway
  title: EdgeGatewayManagementClient
  description: The EdgeGateway Client.
  clear-output-folder: true
```
``` yaml $(python) && $(python-mode) == 'update'
python:
  no-namespace-folders: true
  output-folder: $(python-sdks-folder)/azure-mgmt-edgegateway/azure/mgmt/edgegateway
```
``` yaml $(python) && $(python-mode) == 'create'
python:
  basic-setup-py: true
  output-folder: $(python-sdks-folder)/azure-mgmt-edgegateway
```

## Ruby

See configuration in [readme.ruby.md](./readme.ruby.md)

## Go

See configuration in [readme.go.md](./readme.go.md)

## Java

These settings apply only when `--java` is specified on the command line.
Please also specify `--azure-libraries-for-java-folder=<path to the root directory of your azure-libraries-for-java clone>`.

``` yaml $(java)
java:
  azure-arm: true
  fluent: true
  namespace: com.microsoft.azure.management.edgegateway
  license-header: MICROSOFT_MIT_NO_CODEGEN
  payload-flattening-threshold: 1
  output-folder: $(azure-libraries-for-java-folder)/azure-mgmt-edgegateway
```

### Java multi-api

``` yaml $(java) && $(multiapi)
batch:
  - tag: package-2019-03
```

### Tag: package-2019-03 and java

These settings apply only when `--tag=package-2019-03 --java` is specified on the command line.
Please also specify `--azure-libraries-for-java-folder=<path to the root directory of your azure-sdk-for-java clone>`.

``` yaml $(tag) == 'package-2019-03' && $(java) && $(multiapi)
java:
  namespace: com.microsoft.azure.management.edgegateway.v2018_07_01
  output-folder: $(azure-libraries-for-java-folder)/edgegateway/resource-manager/v2018_07_01
regenerate-manager: true
generate-interface: true
```

# ORT Config

This repository contains [configuration files](https://github.com/oss-review-toolkit/ort#configuration-files) for the
[OSS Review Toolkit](https://github.com/oss-review-toolkit/ort).

## Telekom Notes

The Config is largely on par with the upstream. 
The only current change is the inclusion of [config.yml](./config.yml) to reduce false positives.

## Usage

To use the configuration provided by this repository, it needs to be cloned and used as ORT_CONFIG_DIR.

Set the environment variable ORT_CONFIG_DIR to the cloned repository and then run the relevant ORT commands.

For example, in PowerShell (Windows):

```powershell
$env:ORT_CONFIG_DIR="C:\Users\Username\repos\ort-config"
ort analyze <parameters>
```

Or in Bash (Linux/macOS):

```bash
export ORT_CONFIG_DIR="/home/username/repos/ort-config"
ort analyze <parameters>
```

Using this repository together with ORT will be simplified in future.

## Content

### Curations

The [curations](./curations/) directory contains
[package curations](https://github.com/oss-review-toolkit/ort/blob/main/docs/config-file-curations-yml.md) for
open source packages.

Package curations submitted to this repository must adhere to the following rules:

* Declaring authors and concluded licenses is currently not allowed.
* Declared license mappings must map licenses to valid SPDX expressions. The curation comment must provide proof that
  the mapping is correct.
* Curations that apply to whole namespaces by only setting the type and namespace of the identifier are not allowed.
* The curation file path must be `curations/[type]/[namespace]/[name].yml`. If the namespace is empty, use "_". For
  example a curation for the package `NuGet::Azure.Core:1.2.0` must be in the file `curation/NuGet/_/Azure.Core.yml`.

Package configurations containing license finding curations or path excludes are not yet supported.

### Tools

The [tools](./tools/) directory contains tools that help generating curations.

## Contribute

This repository is currently in incubation and not yet ready for contributions.

# License

Copyright (C) 2019-2024 [The ORT Project Authors](./NOTICE).

See the [LICENSE](./LICENSE) file in the root of this project for license details.

OSS Review Toolkit (ORT) is a [Linux Foundation project](https://www.linuxfoundation.org) and part of
[ACT](https://automatecompliance.org/).

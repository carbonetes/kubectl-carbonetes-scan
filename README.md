[![Carbonetes](https://cdn.carbonetes.com/carbonetes-plugin/assets/branding/branding_header.png)](https://carbonetes.com)

# :bulb: Overview

**Carbonetes Scan** provides comprehensive container analysis and policy evaluation as a fully managed service. Carbonetes analyzes your container images for native code vulnerabilities, software composition analysis (SCA), license types, and secrets.

:pushpin: To know more about Carbonetes, check [our website](https://carbonetes.com).

# `carbonetes scan`: Security Tool for kubectl and oc

![Latest GitHub release](https://img.shields.io/github/release/carbonetes/kubectl-carbonetes-scan.svg)
![GitHub stars](https://img.shields.io/github/stars/ahmetb/kubectx.svg?label=github%20stars)
![Proudly written in Bash](https://img.shields.io/badge/written%20in-bash-ff69b4.svg)

This repository provides `carbonetes-scan` tool.
[Install &rarr;](#dvd-installation)

**`carbonetes-scan`** provides comprehensive container analysis and policy evaluation as a fully managed service. Carbonetes analyzes your container images for native code vulnerabilities, software composition analysis (SCA), license types, and secrets.

To know more about Carbonetes, check [our website](https://carbonetes.com).

# carbonetes-scan

carbonetes-scan is a tool that seamlessly integrates comprehensive container analysis directly into your Kubernetes cluster.

## :pencil: Usage

```sh
~ % kubectl carbonetes scan --help

Carbonetes Scan: Security Tool for kubectl and oc

This plugin provides comprehensive container analysis and policy evaluation as a fully managed service.
Carbonetes analyzes your container images for native code vulnerabilities, software composition analysis (SCA),
license types, and secrets.

Usage:
    kubectl carbonetes scan [flags]

Flags:
  -g, --get-all-images      : List all the unique images inside your cluster

  -h, --help                : help for kubectl-carbonetes-scan

  -i, --image <string>      : the image to be scanned

  -p, --password <string>   : your account password on Carbonetes

  -r, --registry <string>   : your registry uri on Carbonetes

  -u, --username <string>   : the username you are using to login on Carbonetes

  -v, --version             : version for kubectl-carbonetes-scan


Use "kubectl carbonetes scan --image <string> --registry <string> --username <string> --password <string>" to execute a comprehensive container analysis.

You need a valid credentials on Carbonetes to use this plugin.
If you don't have it yet, you can register at: https://carbonetes.com
```

## :exclamation: Prerequisites

This pipe requires a valid **Carbonetes credentials** `(email and password)`.

- Doesn't have any credentials yet? [Register now](https://console.carbonetes.com/register).

## :bulb: Arguments Description

| Argument Name               | Description                                                  |
| --------------------------- | ------------------------------------------------------------ |
| registry \*                 | The registry uri is managed in Carbonetes. |
| image \*                    | The image to be scan. |
| username \*                 | The account username on Carbonetes. |
| password \*                 | The account password on Carbonetes. |

_\* = required inputs._

* :pushpin: Note : to be aligned in your CI/CD pipeline, make sure that you supply the same REPOIMAGETAG that has been built within your pipeline stages.*

## :bulb: Outputs Description

| Output Name                  | Description                                                                                  |
| ---------------------------- | -------------------------------------------------------------------------------------------- |
| Vulnerabilities              | A list of known security risks that can be exploited by a threat actor listed with severities. |
| Software Compositions        | Software that might cause a security risk listed with severities. |
| Software Dependencies        | Pieces of software that rely on each other listed with vulnerability counts. |
| Licenses                     | Legal compliance found on each software of the scanned image. |
| Secrets                      | Secret data found on each software of the scanned image. |
| Policy Result                | The result of the policy evaluation, `PASSED` or `FAILED`. |
| Final Action                 | Recommends if you need to fix all the known vulnerabilities of the scanned image. |

## :dvd: Installation

### :computer: Kubectl Plugins (macOs and Linux)

You can install kubectl-carbonetes-scan using [Krew](https://krew.sigs.k8s.io/), a kubectl plugin manager. `Krew` itself is also a plugin on kubectl. You can easily [install](https://krew.sigs.k8s.io/docs/user-guide/setup/install/) it with only a few steps, available on `MacOS`, `Linux`, and `Windows`.

```sh
$ kubectl krew install carbonetes-scan
```

You can verify the installation using the command `kubectl carbonetes scan --version` to see the version of the installed kubectl plugin.

## :email: Support
To help with this plugin, or have an issue or feature request, please contact: [eng@carbonetes.com](eng@carbonetes.com)

If reporting an issue, please include:

* the version of the plugin
* relevant logs and error messages
* steps to reproduce

## License and Copyright

Copyright © 2021 Carbonetes

Licensed under [MIT License](LICENSE).
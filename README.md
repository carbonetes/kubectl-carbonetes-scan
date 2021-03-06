[![Carbonetes](https://cdn.carbonetes.com/carbonetes-plugin/assets/branding/branding_header.png)](https://carbonetes.com)

# `carbonetes-scan`: Container Security Tool for kubectl and oc

[![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/carbonetes/kubectl-carbonetes-scan)](https://github.com/carbonetes/kubectl-carbonetes-scan/releases)
[![GitHub](https://img.shields.io/github/license/carbonetes/kubectl-carbonetes-scan)](https://github.com/carbonetes/kubectl-carbonetes-scan/blob/main/LICENSE)
![Proudly written in Bash](https://img.shields.io/badge/written%20in-bash-ff69b4.svg)

This repository provides `carbonetes-scan` container security scan tool for Kubernetes cluster.
[Install &rarr;](#dvd-installation)

**`carbonetes-scan`** provides comprehensive container analysis and policy evaluation as a fully managed service. Carbonetes analyzes your container images for native code vulnerabilities, software composition analysis (SCA), license types, malware, secrets and bill of materials.

:pushpin: To know more about Carbonetes, check [our website](https://carbonetes.com).

# carbonetes-scan

carbonetes-scan is a tool that seamlessly integrates complete container analysis directly into your Kubernetes cluster.

## :pencil: Usage

```
~ % kubectl carbonetes-scan --help

Carbonetes Scan: Security Tool for kubectl and oc

This plugin provides comprehensive container analysis and policy evaluation as a fully managed service.
Carbonetes analyzes your container images for native code vulnerabilities, software composition analysis (SCA),
license types, malware, secrets, and bill of materials.

Usage:
    kubectl carbonetes-scan [flags]

Flags:
  -A, --all-namespaces      : List all the unique images on all namespaces

  -h, --help                : help for kubectl-carbonetes-scan

  -i, --image <string>      : the image to be scanned

  -p, --password <string>   : Carbonetes account password

  -r, --registry <string>   : Registry Uri (Added in Carbonetes Web Application)

  -u, --username <string>   : Carbonetes account username

  -v, --version             : version for kubectl-carbonetes-scan


Use "kubectl carbonetes-scan --image <string> --registry <string> --username <string> --password <string>" to execute a complete container analysis.

You need a valid credentials in Carbonetes to use this plugin.
If you don't have it yet, you can register at: https://carbonetes.com
```

## :clipboard: Prerequisites

This plugin requires **Docker installation** and a valid **Carbonetes credentials** `(email and password)`.

- Doesn't have any credentials yet? [Register now](https://console.carbonetes.com/register).

## :bulb: Arguments

| Argument Name               | Description                                                  |
| --------------------------- | ------------------------------------------------------------ |
| registry \*                 | Registry Uri (Added in Carbonetes Web Application) |
| image \*                    | The image to be scanned. |
| username \*                 | The account username in Carbonetes. |
| password \*                 | The account password in Carbonetes. |

_\* = required inputs._

## :bulb: Outputs

| Output Name                  | Description                                                                                  |
| ---------------------------- | -------------------------------------------------------------------------------------------- |
| Vulnerabilities              | A list of known security risks that can be exploited by a threat actor listed with severities. |
| Software Compositions        | Software that might cause a security risk listed with severities. |
| Software Dependencies        | Pieces of software that rely on each other listed with vulnerability counts. |
| Licenses                     | Legal compliance found on each software of the scanned image. |
| Malware                      | Virus threats found on the scanned image. |
| Secrets                      | Secret data found on each software of the scanned image. |
| Bill of Materials            | A list of all the components exist in a software. |
| Policy Result                | The result of the policy evaluation, `PASSED` or `FAILED`. |
| Final Action                 | Recommends if you need to fix all the known vulnerabilities of the scanned image. |

## :dvd: Installation

### :computer: Kubectl Plugins (macOs and Linux)

You can install kubectl-carbonetes-scan using [Krew](https://krew.sigs.k8s.io/), a kubectl plugin manager. `Krew` itself is also a plugin on kubectl. You can easily [install](https://krew.sigs.k8s.io/docs/user-guide/setup/install/) it with only a few steps, available on `MacOS`, `Linux`, and `Windows`.

### via [awesome-kubectl-plugins](https://github.com/ishantanu/awesome-kubectl-plugins)
* Add awesome-kubectl-plugins to Krew
  ```sh
  kubectl krew index add awesome-kubectl-plugins https://github.com/ishantanu/awesome-kubectl-plugins.git
  ```
* Install carbonetes-scan
  ```sh
  kubectl krew install awesome-kubectl-plugins/carbonetes-scan
  ```

### via [Carbonetes Custom Plugin Index](https://github.com/carbonetes/carbonetes-kube-plugin):
* Add the Carbonetes Index
  ```sh
  kubectl krew index add carbonetes https://github.com/carbonetes/carbonetes-kube-plugin.git
  ```
* Install carbonetes-scan
  ```sh
  kubectl krew install carbonetes/carbonetes-scan
  ```

### Download the Manifest:
```sh
curl -sL https://raw.githubusercontent.com/carbonetes/kubectl-carbonetes-scan/main/.krew/carbonetes-scan.yaml > carbonetes-scan.yaml \
  && kubectl krew install --manifest=carbonetes-scan.yaml
```

### Download the Binary:
```sh
  curl -LO https://github.com/carbonetes/kubectl-carbonetes-scan/archive/refs/tags/v1.1.0.tar.gz \
  && tar xf v1.1.0.tar.gz kubectl-carbonetes-scan-1.1.0/kubectl-carbonetes-scan \
  && chmod +x ./kubectl-carbonetes-scan-1.1.0/kubectl-carbonetes-scan \
  && mv -i ./kubectl-carbonetes-scan-1.1.0/kubectl-carbonetes-scan /usr/local/bin/kubectl-carbonetes_scan \
  && rm v1.1.0.tar.gz \
  && rm -rf ./kubectl-carbonetes-scan-1.1.0
```

You can verify the installation using the commands `kubectl plugin list` to see the list of installed plugins or `kubectl carbonetes-scan --version` to see the version of the installed `kubectl-carbonetes-scan`.

## :email: Support
To help with this plugin, or have an issue or feature request, please contact: [eng@carbonetes.com](eng@carbonetes.com)

If reporting an issue, please include:

* the version of the plugin
* relevant logs and error messages
* steps to reproduce

## License and Copyright

Copyright © 2021 Carbonetes

Licensed under [MIT License](LICENSE).
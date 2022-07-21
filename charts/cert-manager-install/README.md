# cert-manager-install For Kubernetes

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v1.8.2](https://img.shields.io/badge/AppVersion-v1.8.2-informational?style=flat-square) ![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Helm](https://img.shields.io/badge/helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)

## Description

A Helm chart for installing and configuring cert-manager
in my home lab environment using Cloudflare, Lets Encrypt
and the ACME DNS01 challenge Cluster Issuer.

## Usage

Please add the estenrye-helm-charts repository before installing any chart provided by this repository:

```bash
helm repo add estenrye-helm-charts https://estenrye.github.io/helm-charts
helm repo update
```

### Installing the Chart

To install the chart with the release name cert-manager-install run:

```bash
helm install cert-manager-install estenrye-helm-charts/cert-manager-install 0.1.0
```

After a few seconds, Bitwarden Directory Connector should be running as a CronJob.

To install the chart in a specific namespace use following commands:

```bash
kubectl create ns cert-manager-install
helm install cert-manager-install estenrye-helm-charts/cert-manager-install --namespace cert-manager-install --version 0.1.0
```

> **Tip**: List all releases using `helm list`, a release is a name used to track a specific deployment

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| acme_email | string | `""` | Sets the email for ACME Certificate Server registration and notifications. |
| acme_server | string | `"https://acme-v02.api.letsencrypt.org/directory"` | Sets the target ACME Server to send certificate requests. |
| cert-manager.enabled | bool | `false` |  |
| cert-manager.global.logLevel | int | `2` | Set the verbosity of cert-manager. Range of 0 - 6 with 6 being the most verbose. |
| cert-manager.installCRDs | bool | `true` | When true, installs the cert-manager CRDs |
| cert-manager.podDnsConfig.nameservers[0] | string | `"1.1.1.1"` |  |
| cert-manager.podDnsConfig.nameservers[1] | string | `"1.0.0.1"` |  |
| cert-manager.podDnsPolicy | string | `"None"` |  |
| cloudflare_api_token | string | `""` | Sets the Cloudflare API Token for DNS-01 challenges |

## Source Code

* <https://github.com/estenrye/helm-charts/tree/main/charts/cert-manager-install>
* <https://github.com/cert-manager/cert-manager>

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.jetstack.io | cert-manager | v1.8.2 |

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Esten Rye |  | https://github.com/estenrye |

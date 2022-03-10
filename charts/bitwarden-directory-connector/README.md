# Bitwarden Directory Connector for Kubernetes

![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-informational?style=for-the-badge)
![Type: application](https://img.shields.io/badge/Type-application-informational?style=for-the-badge)
![AppVersion: v0.0.20](https://img.shields.io/badge/AppVersion-v0.0.20-informational?style=for-the-badge)

![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Alpine Linux 3.15.0](https://img.shields.io/badge/alpine_linux_3.15.0-0D597F?style=for-the-badge&logo=alpine-linux&logoColor=white)
![Helm](https://img.shields.io/badge/helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)

## Legal Disclaimer 👮

This project is not affiliated with Bitwarden Inc or the Bitwarden brand.

"Bitwarden" is a trademark of Bitwarden Inc.

Other trademarks referenced herein are property of their respective owners.# bitwarden-directory-connector For Kubernetes
## Description

This Helm Chart installs the Bitwarden Directory Connector as a
CronJob on a Kubernetes cluster.  It uses the `estenrye/bwdc`
docker image.

## Usage

Please add the estenrye-helm-charts repository before installing any chart provided by this repository:

```bash
helm repo add estenrye-helm-charts https://estenrye.github.io/helm-charts
helm repo update
```

### Installing the Chart

To install the chart with the release name bitwarden-directory-connector run:

```bash
helm install bitwarden-directory-connector estenrye-helm-charts/bitwarden-directory-connector 0.0.1
```

After a few seconds, Bitwarden Directory Connector should be running as a CronJob.

To install the chart in a specific namespace use following commands:

```bash
kubectl create ns bitwarden-directory-connector
helm install bitwarden-directory-connector estenrye-helm-charts/bitwarden-directory-connector --namespace bitwarden-directory-connector --version 0.0.1
```

> **Tip**: List all releases using `helm list`, a release is a name used to track a specific deployment

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"nginx"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| tolerations | list | `[]` |  |

## Source Code

* <https://github.com/estenrye/helm-charts/tree/main/charts/bitwarden-directory-connector>
* <https://github.com/estenrye/docker-bwdc>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Esten Rye |  | https://github.com/estenrye |

**Homepage:** <https://github.com/estenrye/helm-charts>
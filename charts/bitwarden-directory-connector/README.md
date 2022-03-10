# Bitwarden Directory Connector for Kubernetes

![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-informational?style=for-the-badge)
![Type: application](https://img.shields.io/badge/Type-application-informational?style=for-the-badge)
![AppVersion: v0.0.20](https://img.shields.io/badge/AppVersion-v0.0.20-informational?style=for-the-badge)

![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Alpine Linux 3.15.0](https://img.shields.io/badge/alpine_linux_3.15.0-0D597F?style=for-the-badge&logo=alpine-linux&logoColor=white)
![Helm](https://img.shields.io/badge/helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)

## Description

This Helm Chart installs the Bitwarden Directory Connector as a
CronJob on a Kubernetes cluster.  It uses the `estenrye/bwdc`
docker image.

Related Links
  - [About Bitwarden Directory Connector](https://bitwarden.com/help/directory-sync/)
  - [Bitwarden Directory Connector CLI Documentation](https://bitwarden.com/help/directory-sync-cli/)
  - [Bitwarden Directory Connector GitHub Repository](https://github.com/bitwarden/directory-connector)
  - [estenrye/bwdc Docker Image GitHub Repository](https://github.com/estenrye/docker-bwdc)

## Usage

Please add the estenrye-helm-charts repository before installing any chart provided by this repository:

```bash
helm repo add estenrye-helm-charts https://estenrye.github.io/helm-charts
helm repo update
```

### Installing the Chart

To install the chart with the release name minecraft-exporter run:

```bash
helm install bwdc estenrye-helm-charts/bitwarden-directory-connector --version 0.0.1
```

After a few seconds, Bitwarden Directory Connector should be running as a CronJob.

To install the chart in a specific namespace use following commands:

```bash
kubectl create ns bitwarden
helm install bwdc estenrye-helm-charts/bitwarden-directory-connector --namespace bitwarden --version 0.0.1
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

## Legal Disclaimer 👮

This project is not affiliated with Bitwarden Inc or the Bitwarden brand.

"Bitwarden" is a trademark of Bitwarden Inc.

Other trademarks referenced herein are property of their respective owners.# bitwarden-directory-connector

![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v0.0.20](https://img.shields.io/badge/AppVersion-v0.0.20-informational?style=flat-square)

This Helm Chart installs the Bitwarden Directory Connector as a
CronJob on a Kubernetes cluster.  It uses the `estenrye/bwdc`
docker image.

Related Links
  - [About Bitwarden Directory Connector](https://bitwarden.com/help/directory-sync/)
  - [Bitwarden Directory Connector CLI Documentation](https://bitwarden.com/help/directory-sync-cli/)
  - [Bitwarden Directory Connector GitHub Repository](https://github.com/bitwarden/directory-connector)
  - [estenrye/bwdc Docker Image GitHub Repository](https://github.com/estenrye/docker-bwdc)

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

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.7.0](https://github.com/norwoodj/helm-docs/releases/v1.7.0)

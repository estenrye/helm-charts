# bitwarden-directory-connector For Kubernetes

![Version: 0.0.4](https://img.shields.io/badge/Version-0.0.4-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v0.0.20](https://img.shields.io/badge/AppVersion-v0.0.20-informational?style=flat-square) ![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Alpine Linux 3.15.0](https://img.shields.io/badge/alpine_linux_3.15.0-0D597F?style=for-the-badge&logo=alpine-linux&logoColor=white)
![Helm](https://img.shields.io/badge/helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)

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
helm install bitwarden-directory-connector estenrye-helm-charts/bitwarden-directory-connector 0.0.4
```

After a few seconds, Bitwarden Directory Connector should be running as a CronJob.

To install the chart in a specific namespace use following commands:

```bash
kubectl create ns bitwarden-directory-connector
helm install bitwarden-directory-connector estenrye-helm-charts/bitwarden-directory-connector --namespace bitwarden-directory-connector --version 0.0.4
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
| bitwarden.organization.client-id | string | `"organization.b5351047-89b6-820f-ad21016b6222"` | The Bitwarden API Client Id for the Organization. You must replace the value in this field.  You can find this by navigating to your Bitwarden Organization Settings and clicking View API Key. |
| bitwarden.organization.client-secret | string | `"yUMB4trbqV1bavhEHGqbuGpz4AlHm9"` | The Bitwarden API Client Secret for the Organization. You must replace the value in this field.  You can find this by navigating to your Bitwarden Organization Settings and clicking View API Key. |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | Configures the image pull policy.  Valid options include [`Always`, `IfNotPresent`, `Never`] |
| image.repository | string | `"estenrye/bwdc"` | Docker Image Repository Name. |
| image.tag | string | `nil` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| tolerations | list | `[]` |  |

## Source Code

* <https://github.com/estenrye/helm-charts/tree/main/charts/bitwarden-directory-connector>
* <https://github.com/estenrye/docker-bwdc>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Esten Rye |  | https://github.com/estenrye |

**Homepage:** <https://github.com/estenrye/helm-charts>
# bitwarden-directory-connector

![Version: 0.0.4](https://img.shields.io/badge/Version-0.0.4-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v0.0.20](https://img.shields.io/badge/AppVersion-v0.0.20-informational?style=flat-square)

This Helm Chart installs the Bitwarden Directory Connector as a
CronJob on a Kubernetes cluster.  It uses the `estenrye/bwdc`
docker image.

**Homepage:** <https://github.com/estenrye/helm-charts>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Esten Rye |  | https://github.com/estenrye |

## Source Code

* <https://github.com/estenrye/helm-charts/tree/main/charts/bitwarden-directory-connector>
* <https://github.com/estenrye/docker-bwdc>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| bitwarden.organization.client-id | string | `"organization.b5351047-89b6-820f-ad21016b6222"` | The Bitwarden API Client Id for the Organization. You must replace the value in this field.  You can find this by navigating to your Bitwarden Organization Settings and clicking View API Key. |
| bitwarden.organization.client-secret | string | `"yUMB4trbqV1bavhEHGqbuGpz4AlHm9"` | The Bitwarden API Client Secret for the Organization. You must replace the value in this field.  You can find this by navigating to your Bitwarden Organization Settings and clicking View API Key. |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | Configures the image pull policy.  Valid options include [`Always`, `IfNotPresent`, `Never`] |
| image.repository | string | `"estenrye/bwdc"` | Docker Image Repository Name. |
| image.tag | string | `nil` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.7.0](https://github.com/norwoodj/helm-docs/releases/v1.7.0)

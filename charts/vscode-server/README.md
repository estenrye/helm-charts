# vscode-server For Kubernetes

![Version: 0.2.0](https://img.shields.io/badge/Version-0.2.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 4.4.0](https://img.shields.io/badge/AppVersion-4.4.0-informational?style=flat-square) ![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Helm](https://img.shields.io/badge/helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)

## Description

A Helm chart for Kubernetes

## Usage

Please add the estenrye-helm-charts repository before installing any chart provided by this repository:

```bash
helm repo add estenrye-helm-charts https://estenrye.github.io/helm-charts
helm repo update
```

### Installing the Chart

To install the chart with the release name vscode-server run:

```bash
helm install vscode-server estenrye-helm-charts/vscode-server 0.2.0
```

After a few seconds, Bitwarden Directory Connector should be running as a CronJob.

To install the chart in a specific namespace use following commands:

```bash
kubectl create ns vscode-server
helm install vscode-server estenrye-helm-charts/vscode-server --namespace vscode-server --version 0.2.0
```

> **Tip**: List all releases using `helm list`, a release is a name used to track a specific deployment

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | Configures the image pull policy.  Valid options include [`Always`, `IfNotPresent`, `Never`] |
| image.repository | string | `"linuxserver/code-server"` | Docker Image Repository Name. |
| image.tag | string | `""` | (string) Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | image pull secrets to retrieve image if required. |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"code-server.cluster.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"Prefix"` |  |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| password.enabled | bool | `false` | When true, enables creation of secret containing the code server password and mapping of that secret to the PASSWORD environment variable. |
| password.value | string | `""` | Value of the password to set and map to the PASSWORD environment variable. |
| persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| persistence.annotations | object | `{}` |  |
| persistence.dataSource | object | `{}` |  |
| persistence.enabled | bool | `false` |  |
| persistence.resources.requests.storage | string | `"10Gi"` |  |
| persistence.storageClassName | string | `""` |  |
| podAnnotations | object | `{}` | map of annotations to apply to the pod. |
| podSecurityContext | object | `{}` | map of pod security context settings to apply to the pod. |
| replicaCount | int | `1` | Number of replicas to provision. |
| resources | object | `{}` |  |
| securityContext | object | `{}` | map of security context settings to apply to the pod. |
| service.containerPort | int | `8443` | port the service should sent traffic to. |
| service.port | int | `80` | port the service should receive traffic on. |
| service.type | string | `"ClusterIP"` | specifies the Kubernetes Service type to create. |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` |  |

## Source Code

* <https://github.com/estenrye/helm-charts/tree/main/charts/vscode-server>
* <https://github.com/cdr/code-server>
* <https://github.com/linuxserver/docker-code-server>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Esten Rye |  | https://github.com/estenrye |

# vscode-server For Kubernetes

![Version: 0.3.0](https://img.shields.io/badge/Version-0.3.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 4.4.0](https://img.shields.io/badge/AppVersion-4.4.0-informational?style=flat-square) ![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
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
helm install vscode-server estenrye-helm-charts/vscode-server 0.3.0
```

After a few seconds, Bitwarden Directory Connector should be running as a CronJob.

To install the chart in a specific namespace use following commands:

```bash
kubectl create ns vscode-server
helm install vscode-server estenrye-helm-charts/vscode-server --namespace vscode-server --version 0.3.0
```

> **Tip**: List all releases using `helm list`, a release is a name used to track a specific deployment

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| docker_daemon.fullnameOverride | string | `""` |  |
| docker_daemon.image.pullPolicy | string | `"IfNotPresent"` | Configures the image pull policy for Docker Daemon.  Valid options include [`Always`, `IfNotPresent`, `Never`] |
| docker_daemon.image.repository | string | `"docker"` | Docker Daemon Image Repository Name. |
| docker_daemon.image.tag | string | `"dind-rootless"` | (string) Overrides the image tag for Docker Daemon whose default is `dind-rootless`. |
| docker_daemon.nameOverride | string | `""` |  |
| docker_daemon.resources | object | `{}` |  |
| docker_daemon.securityContext | object | `{}` | map of security context settings to apply to the pod. |
| fullnameOverride | string | `""` |  |
| imagePullSecrets | list | `[]` | image pull secrets to retrieve image if required. |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` | map of annotations to apply to the pod. |
| podSecurityContext | object | `{}` | map of pod security context settings to apply to the pod. |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` |  |
| vscode_server.fullnameOverride | string | `""` |  |
| vscode_server.image.pullPolicy | string | `"IfNotPresent"` | Configures the image pull policy for Visual Studio Code Server.  Valid options include [`Always`, `IfNotPresent`, `Never`] |
| vscode_server.image.repository | string | `"linuxserver/code-server"` | Visual Studio Code Server Image Repository Name. |
| vscode_server.image.tag | string | `""` | (string) Overrides the image tag for Visual Studio Code Server whose default is the chart appVersion. |
| vscode_server.ingress.annotations | object | `{}` |  |
| vscode_server.ingress.className | string | `""` |  |
| vscode_server.ingress.enabled | bool | `false` |  |
| vscode_server.ingress.hosts[0].host | string | `"code-server.cluster.local"` |  |
| vscode_server.ingress.hosts[0].paths[0].path | string | `"/"` |  |
| vscode_server.ingress.hosts[0].paths[0].pathType | string | `"Prefix"` |  |
| vscode_server.ingress.tls | list | `[]` |  |
| vscode_server.nameOverride | string | `""` |  |
| vscode_server.password.enabled | bool | `false` | When true, enables creation of secret containing the code server password and mapping of that secret to the PASSWORD environment variable. |
| vscode_server.password.value | string | `""` | Value of the password to set and map to the PASSWORD environment variable. |
| vscode_server.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| vscode_server.persistence.annotations | object | `{}` |  |
| vscode_server.persistence.dataSource | object | `{}` |  |
| vscode_server.persistence.enabled | bool | `false` |  |
| vscode_server.persistence.resources.requests.storage | string | `"10Gi"` |  |
| vscode_server.persistence.storageClassName | string | `""` |  |
| vscode_server.replicaCount | int | `1` | Number of replicas to provision. |
| vscode_server.resources | object | `{}` |  |
| vscode_server.securityContext | object | `{}` | map of security context settings to apply to the pod. |
| vscode_server.service.containerPort | int | `8443` | port the service should sent traffic to. |
| vscode_server.service.port | int | `80` | port the service should receive traffic on. |
| vscode_server.service.type | string | `"ClusterIP"` | specifies the Kubernetes Service type to create. |

## Source Code

* <https://github.com/estenrye/helm-charts/tree/main/charts/vscode-server>
* <https://github.com/cdr/code-server>
* <https://github.com/linuxserver/docker-code-server>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Esten Rye |  | https://github.com/estenrye |

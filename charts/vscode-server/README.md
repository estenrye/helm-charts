# vscode-server For Kubernetes

![Version: 0.4.0](https://img.shields.io/badge/Version-0.4.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 4.4.0](https://img.shields.io/badge/AppVersion-4.4.0-informational?style=flat-square) ![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
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
helm install vscode-server estenrye-helm-charts/vscode-server 0.4.0
```

After a few seconds, Bitwarden Directory Connector should be running as a CronJob.

To install the chart in a specific namespace use following commands:

```bash
kubectl create ns vscode-server
helm install vscode-server estenrye-helm-charts/vscode-server --namespace vscode-server --version 0.4.0
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
| podSecurityContext | object | `{"fsGroup":1000}` | map of pod security context settings to apply to the pod. |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| step-certificates.inject.certificates.intermediate_ca | string | `nil` |  |
| step-certificates.inject.certificates.root_ca | string | `nil` |  |
| step-certificates.inject.config.files."ca.json".address | string | `"0.0.0.0:9000"` |  |
| step-certificates.inject.config.files."ca.json".authority.provisioners | list | `[]` |  |
| step-certificates.inject.config.files."ca.json".crt | string | `"/home/step/certs/intermediate_ca.crt"` |  |
| step-certificates.inject.config.files."ca.json".db.dataSource | string | `"/home/step/db"` |  |
| step-certificates.inject.config.files."ca.json".db.type | string | `"badgerv2"` |  |
| step-certificates.inject.config.files."ca.json".dnsNames[0] | string | `"code-server-step-ca.services.default.example.com"` |  |
| step-certificates.inject.config.files."ca.json".dnsNames[1] | string | `"code-server-step-certificates.default.svc.cluster.local"` |  |
| step-certificates.inject.config.files."ca.json".dnsNames[2] | string | `"code-server-step-certificates.svc.cluster.local"` |  |
| step-certificates.inject.config.files."ca.json".dnsNames[3] | string | `"127.0.0.1"` |  |
| step-certificates.inject.config.files."ca.json".federateRoots | list | `[]` |  |
| step-certificates.inject.config.files."ca.json".key | string | `"/home/step/secrets/intermediate_ca_key"` |  |
| step-certificates.inject.config.files."ca.json".logger.format | string | `"json"` |  |
| step-certificates.inject.config.files."ca.json".root | string | `"/home/step/certs/root_ca.crt"` |  |
| step-certificates.inject.config.files."ca.json".tls.cipherSuites[0] | string | `"TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256"` |  |
| step-certificates.inject.config.files."ca.json".tls.cipherSuites[1] | string | `"TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256"` |  |
| step-certificates.inject.config.files."ca.json".tls.maxVersion | float | `1.3` |  |
| step-certificates.inject.config.files."ca.json".tls.minVersion | float | `1.2` |  |
| step-certificates.inject.config.files."ca.json".tls.renegotiation | bool | `false` |  |
| step-certificates.inject.config.files."defaults.json".ca-config | string | `"/home/step/config/ca.json"` |  |
| step-certificates.inject.config.files."defaults.json".ca-url | string | `"https://step-ca.svc.cluster.local"` |  |
| step-certificates.inject.config.files."defaults.json".fingerprint | string | `nil` |  |
| step-certificates.inject.config.files."defaults.json".root | string | `"/home/step/certs/root_ca.crt"` |  |
| step-certificates.inject.enabled | bool | `true` |  |
| step-certificates.inject.secrets.ca_password | string | `nil` |  |
| step-certificates.inject.secrets.provisioner_password | string | `nil` |  |
| step-certificates.inject.secrets.x509.intermediate_ca_key | string | `nil` |  |
| step-certificates.inject.secrets.x509.root_ca_key | string | `nil` |  |
| tags | object | `{"install-cert-manager":false,"install-step-issuer":false}` | step-certificates injects configuration for step-ca to generate run the following command: `step ca init --helm --deployment-type=standalone --name=vscode-server-ca --dns=step-ca.svc.cluster.local --address=:443 --provisioner=step-ca-provisioner > values.yml` |
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

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.jetstack.io | cert-manager | v1.8.0 |
| https://smallstep.github.io/helm-charts/ | step-certificates | 1.18.2+20220324 |
| https://smallstep.github.io/helm-charts/ | step-issuer | 0.6.4 |

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Esten Rye |  | https://github.com/estenrye |

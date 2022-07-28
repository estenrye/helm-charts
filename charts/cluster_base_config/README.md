# cluster_base_config For Kubernetes

![Version: 0.1.1](https://img.shields.io/badge/Version-0.1.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square) ![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Helm](https://img.shields.io/badge/helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)

## Description

A Helm chart for installing common configuration data.

## Usage

Please add the estenrye-helm-charts repository before installing any chart provided by this repository:

```bash
helm repo add estenrye-helm-charts https://estenrye.github.io/helm-charts
helm repo update
```

### Installing the Chart

To install the chart with the release name cluster_base_config run:

```bash
helm install cluster_base_config estenrye-helm-charts/cluster_base_config 0.1.1
```

After a few seconds, Bitwarden Directory Connector should be running as a CronJob.

To install the chart in a specific namespace use following commands:

```bash
kubectl create ns cluster_base_config
helm install cluster_base_config estenrye-helm-charts/cluster_base_config --namespace cluster_base_config --version 0.1.1
```

> **Tip**: List all releases using `helm list`, a release is a name used to track a specific deployment

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| cluster_name | string | `""` | name of the cluster |
| ingress_nginx_load_balancer_ip | string | `""` | ip address for ingress-nginx controller load balacer service |
| top_level_domain | string | `"example.com"` | top level domain to use in dns suffixes |


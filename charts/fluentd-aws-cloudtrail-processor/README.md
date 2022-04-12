# fluentd-aws-cloudtrail-processor For Kubernetes

![Version: 0.0.4](https://img.shields.io/badge/Version-0.0.4-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: latest](https://img.shields.io/badge/AppVersion-latest-informational?style=flat-square) ![Docker](https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Alpine Linux 3.14.0](https://img.shields.io/badge/alpine_linux_3.14.0-0D597F?style=for-the-badge&logo=alpine-linux&logoColor=white)
![Helm](https://img.shields.io/badge/helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)

## Description

This Helm Chart installs FluentD and connects it to an AWS SQS Queue
and AWS S3 Bucket to consume AWS Cloudtrail logs and Push them to an
EFK Instance.

## Usage

Please add the estenrye-helm-charts repository before installing any chart provided by this repository:

```bash
helm repo add estenrye-helm-charts https://estenrye.github.io/helm-charts
helm repo update
```

### Installing the Chart

To install the chart with the release name fluentd-aws-cloudtrail-processor run:

```bash
helm install fluentd-aws-cloudtrail-processor estenrye-helm-charts/fluentd-aws-cloudtrail-processor 0.0.4
```

After a few seconds, Bitwarden Directory Connector should be running as a CronJob.

To install the chart in a specific namespace use following commands:

```bash
kubectl create ns fluentd-aws-cloudtrail-processor
helm install fluentd-aws-cloudtrail-processor estenrye-helm-charts/fluentd-aws-cloudtrail-processor --namespace fluentd-aws-cloudtrail-processor --version 0.0.4
```

> **Tip**: List all releases using `helm list`, a release is a name used to track a specific deployment

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| automountServiceAccountToken | bool | `false` | When true, Service Account Token is automounted. |
| fluentd.aws_access_key_id | string | `"YOUR_AWS_ACCESS_ID_HERE"` | The AWS IAM Access Key Id used to access the S3 bucket and SQS queue. |
| fluentd.aws_region | string | `"us-west-2"` | The AWS Region hosting the S3 Bucket and SQS queue. |
| fluentd.aws_secret_access_key | string | `"YOUR_AWS_SECRET_ACCESS_KEY_HERE"` | The AWS IAM Secret Access Key used to access the S3 bucket and SQS queue. |
| fluentd.s3_bucket | string | `"YOUR_S3_BUCKET_NAME_HERE"` | The AWS S3 Bucket that contains your AWS Cloudtrail Logs. |
| fluentd.sqs_queue | string | `"YOUR_SQS_QUEUE_NAME_HERE"` | The AWS SQS Queue that receives AWS S3 Bucket Notifications |
| fluentd.sqs_retry_error_interval | int | `300` | Number of seconds to wait between retrying errrors. |
| fluentd.sqs_skip_delete | bool | `false` | When true, fluentd skips deletion of messages from the queue. |
| fluentd.sqs_wait_time_seconds | int | `20` | Number of seconds to wait before polling the SQS queue. |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | Configures the image pull policy.  Valid options include [`Always`, `IfNotPresent`, `Never`] |
| image.repository | string | `"docker.io/estenrye/fluentd-cloudtrail"` | Docker Image Repository Name. |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | image pull secrets to retrieve image if required. |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` | map of annotations to apply to the pod. |
| podSecurityContext | object | `{}` | map of pod security context settings to apply to the pod. |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` | map of security context settings to apply to the pod. |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `false` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` |  |

## Source Code

* <https://github.com/estenrye/helm-charts/tree/main/charts/fluentd-aws-cloudtrail-processor>
* <https://github.com/estenrye/slides/docker/estenrye/fluentd-cloudtrail>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Esten Rye |  | https://github.com/estenrye |

**Homepage:** <https://github.com/estenrye/helm-charts>
# fluentd-aws-cloudtrail-processor

![Version: 0.0.4](https://img.shields.io/badge/Version-0.0.4-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: latest](https://img.shields.io/badge/AppVersion-latest-informational?style=flat-square)

This Helm Chart installs FluentD and connects it to an AWS SQS Queue
and AWS S3 Bucket to consume AWS Cloudtrail logs and Push them to an
EFK Instance.

**Homepage:** <https://github.com/estenrye/helm-charts>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Esten Rye |  | https://github.com/estenrye |

## Source Code

* <https://github.com/estenrye/helm-charts/tree/main/charts/fluentd-aws-cloudtrail-processor>
* <https://github.com/estenrye/slides/docker/estenrye/fluentd-cloudtrail>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| automountServiceAccountToken | bool | `false` | When true, Service Account Token is automounted. |
| fluentd.aws_access_key_id | string | `"YOUR_AWS_ACCESS_ID_HERE"` | The AWS IAM Access Key Id used to access the S3 bucket and SQS queue. |
| fluentd.aws_region | string | `"us-west-2"` | The AWS Region hosting the S3 Bucket and SQS queue. |
| fluentd.aws_secret_access_key | string | `"YOUR_AWS_SECRET_ACCESS_KEY_HERE"` | The AWS IAM Secret Access Key used to access the S3 bucket and SQS queue. |
| fluentd.s3_bucket | string | `"YOUR_S3_BUCKET_NAME_HERE"` | The AWS S3 Bucket that contains your AWS Cloudtrail Logs. |
| fluentd.sqs_queue | string | `"YOUR_SQS_QUEUE_NAME_HERE"` | The AWS SQS Queue that receives AWS S3 Bucket Notifications |
| fluentd.sqs_retry_error_interval | int | `300` | Number of seconds to wait between retrying errrors. |
| fluentd.sqs_skip_delete | bool | `false` | When true, fluentd skips deletion of messages from the queue. |
| fluentd.sqs_wait_time_seconds | int | `20` | Number of seconds to wait before polling the SQS queue. |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | Configures the image pull policy.  Valid options include [`Always`, `IfNotPresent`, `Never`] |
| image.repository | string | `"docker.io/estenrye/fluentd-cloudtrail"` | Docker Image Repository Name. |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | image pull secrets to retrieve image if required. |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` | map of annotations to apply to the pod. |
| podSecurityContext | object | `{}` | map of pod security context settings to apply to the pod. |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` | map of security context settings to apply to the pod. |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `false` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.7.0](https://github.com/norwoodj/helm-docs/releases/v1.7.0)

# helm-chart-fluentd

[![](https://dockerbuildbadges.quelltext.eu/status.svg?organization=nachomillangarcia&repository=fluentd-k8s)](https://hub.docker.com/r/nachomillangarcia/fluentd-k8s/builds/)

Helm chart and Dockerfile to deploy Fluentd. It includes configuration and plugins to integrate with Kubernetes metadata

## Dockerfile
See docker folder. It includes Fluentd v0.14.25 and the following plugins:

- [Kubernetes metadata filter](https://github.com/fabric8io/fluent-plugin-kubernetes_metadata_filter)
- [Kubernetes parser](https://github.com/fluent/fluentd-kubernetes-daemonset/blob/master/docker-image/v0.12/alpine-s3/plugins/parser_kubernetes.rb)
- [Record Modifier](https://github.com/repeatedly/fluent-plugin-record-modifier)
- [ElasticSearch Output](https://docs.fluentd.org/v1.0/articles/out_elasticsearch)
- [S3 Output](https://docs.fluentd.org/v0.12/articles/out_s3)
- [GELF Output](https://github.com/emsearcy/fluent-plugin-gelf)

Autometed builds of this Dockerfile are available in [DockerHub](https://hub.docker.com/r/nachomillangarcia/fluentd-k8s/)

## Helm Chart
See helm folder. It create a daemonset, a configmap with fluentd configuration, and a RBAC setup for fluentd pods. **WARNING**: By default it grants cluster-admin permissions.

### Deploy
```
cd helm
helm install .
```

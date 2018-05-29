# FLUENTD DAEMONSET

Chart to deploy [Fluentd](https://www.fluentd.org/) on Kubernetes as a [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/). It comes with RBAC and tolerations config and allows custom configuration for sources, filters and outputs.

## Installing the Chart
```
helm install --name my-fluentd .
```

## Configuration

The following table lists the configurable parameters of the heptio-ark chart and their default values.

| Parameter | Description | Rquired | Default |
| --------- | ----------- | ------- | ------- |
| `image` | image and tag to deploy | yes | nachomillangarcia/fluentd-k8s |
| `tolerations` | Array of [Pod tolerations](https://kubernetes.io/docs/concepts/configuration/taint-and-toleration/) | no | [operator: "Exists"]|
| `resources` | pod resources map | no | See values.yaml |
| `clusterRole` | clusterRole for RBAC Configuration| yes | cluster-admins |
| `sources` | Fluentd sources config | no | See values.yaml |
| `filters` | Fluentd filters config | no | See values.yaml |
| `outputs` | Fluentd sources config | no | See values.yaml |

## Other Charts
Official incubator repo: https://github.com/kubernetes/charts/tree/master/incubator/fluentd

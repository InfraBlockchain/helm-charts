# Infra Para Helm Chart

The helm chart installs the [Infrablockspace](https://github.com/InfraBlockchain/infrablockspace-sdk).

![Version: 1.0.4](https://img.shields.io/badge/Version-1.0.4-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.1.0](https://img.shields.io/badge/AppVersion-0.1.0-informational?style=flat-square)


## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| devops | <devops@bc-labs.net> | <https://github.com/InfraBlockspace/helm-charts> |


## Installing the chart

```console
helm repo add infrablockchain https://infrablockchain.github.io/helm-charts/
helm install infra-para infrablockchain/infra-para
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
 affinity | object | `{}` |  Assign custom affinity rules |
| ingress | object | `{"annotations":{},"className":"","enabled":false,"hosts":[{"host":"chart-example.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[{"hosts":["chart-example.local"],"secretName":"chart-example-tls"}]}` | Creates an ingress resource |
| ingress.annotations | object | `{}` | Annotations to add to the Ingress |
| ingress.className | string | `""` | 	Ingress class name  |
| ingress.enabled | bool | `false` | Enable creation of Ingress  |
| ingress.hosts | list | `[{"host":"chart-example.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}]` | A list of hosts for the Ingress  |
| ingress.tls | list | `[{"hosts":["chart-example.local"],"secretName":"chart-example-tls"}]` | Ingress TLS configuration  |
|node| object | `{}` | Deploy a substrate node. ref: https://docs.substrate.io/tutorials/v3/private-network/ |
| node.archive | bool | `false` | if set, start archiving the node |
| node.boot.enable | bool | `true` | if set, start bootnode |
| node.bootnodes | list | `[]` | Parachain peer url list |
| node.chainData.enable | bool | `true` | if set, create persistante volume claim and use it to store ParaChain data  |
| node.chainData.kubernetesVolumeSnapshot | string | `nil` | If set, create a clone of the volume (using volumeClaimTemplates.dataSource.VolumeSnapshot) and use it to store Parachain data |
| node.chainData.kubernetesVolumeToClone | string | `nil` | If set, create a clone of the volume (using volumeClaimTemplates.dataSource.PersistentVolumeClaim) and use it to store Parachain data |
| node.chainData.storageClass | string | `""` | Storage class to use for persistent volume  |
| node.chainData.volumeSize | string | `"100Gi"` | Size of the volume for Parachain data |
| node.keys | list | `[]` | Keys to use by the node |
| node.relay.bootnodes | list | `[]` | Relaychain peer url list |
| node.relay.chainData.enable | bool | `true` | if set, create persistante volume claim and use it to store RelayChain data |
| node.relay.chainData.kubernetesVolumeSnapshot | string | `nil` | If set, create a clone of the volume (using volumeClaimTemplates.dataSource.VolumeSnapshot) and use it to store Relaychain data |
| node.relay.chainData.kubernetesVolumeToClone | string | `nil` | If set, create a clone of the volume (using volumeClaimTemplates.dataSource.PersistentVolumeClaim) and use it to store Relaychain data |
| node.relay.chainData.storageClass | string | `""` | Storage class to use for persistent volume  |
| node.relay.chainData.volumeSize | string | `"100Gi"` | Size of the volume for Relaychain data |
| node.relay.spec.url | string | `""` |URL to retrive Relaychain spec  |
| node.spec.url | string | `""` | URL to retrive Parachain spec |
| nodeSelector | object | `{}` | {}	Define which Nodes the Pods are scheduled on. |
| podAnnotations | object | `{}` | 	Annotations to add to the pod |
| resources | object | `{}` | 	Resource limits & requests |
| service.port.peer | int | `30333` | InfrablockSpace Peer Port |
| service.port.rpc | int | `9944` | InfrablockSpace Rpc Port |
| service.type | string | `"ClusterIP"` | Service type |
| serviceAccount | object | `{}` | Service account for the pod to use ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/ |
| serviceAccount.annotations | object | `{}` | Annotations to add to the ServiceAccount resource  |
| serviceAccount.create | bool | `true` | Enable the creation of a ServiceAccount for InfrablockSpace pods  |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tag | int | `3` | infrablockspace image tag |
| terminationGracePeriodSeconds | int | `10` | In seconds, time the given to the InfrablockSpace pod needs to terminate gracefully  |
| tolerations | list | `[]` | Tolerations for use with node taints |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.3](https://github.com/norwoodj/helm-docs/releases/v1.11.3)
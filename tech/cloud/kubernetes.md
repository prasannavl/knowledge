# Kubernetes

## Resources

- https://linuxacademy.com/blog/containers/kubernetes-cheat-sheet/?utm_source=intercom&utm_medium=email&utm_campaign=2019_learnbydoing
- https://gist.github.com/MikeSchuette/b23f88d6c16ce5b6913169685acc662d
- https://docs.microsoft.com/en-us/azure/aks/concepts-clusters-workloads
- https://cloud.google.com/kubernetes-engine/docs/concepts

## Platforms

### GCP GKS

- Option of `Google Container OS` or `Ubuntu` with docker containers.
- Optionally performs automatic node upgrades in a controlled manner making it closer to maintenance free.
- Most controlled and most affordable cost structure.

### Azure AKS

- `Ubuntu` with `Moby` (docker) containers.  
- Need to use [`Kured`](https://github.com/weaveworks/kured) for node maintenance.
- Well controlled cost structure.
- [`aks-engine`](https://github.com/Azure/aks-engine) can be used for manually controlled Kubernetes master.
- `ACI` as an extension of AKS through virtual nodes for burst scaling is quite useful.

### AWS EKS

- `Amazon Linux` with docker containers.
- Need to use [`Kured`](https://github.com/weaveworks/kured) for node maintenance.
- Lots of internal costs in the ecosystem - expensive ELBs, CloudTrail Logs (even for internal Kubernetes logs).

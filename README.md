# k8s-ext
Config for **Kubernetes** container orchestration.
Generally specific to **Anchorlytics** compute infrastructure.
This repository is for the **external** cluster, publicly accessible via ingress.

Most manifests use the [Helm chart CRD](https://rancher.com/docs/k3s/latest/en/helm/).

**Secrets** referenced in these charts are defined in a separate private repo.

## Special Directories
+ `.ns/`: create **namespaces**
+ `.util/`: one-off **utility** pods for troubleshooting

## Usage
+ Add cluster nodes to ansible **inventory**
+ Install **k3s** on cluster nodes with [ho-ansible/k3s](https://github.com/ho-ansible/k3s)
+ Create **namespaces**:
```
kubectl apply -f .ns/
```
+ Create desired **resources**: e.g., 
```
kubectl apply -f ingress-nginx.yaml
```

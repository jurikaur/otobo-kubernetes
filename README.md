# otobo-kubernetes
OTOBO repository for Kubernetes
Elasticsearch do not work, pod constanly crashing. Java error.

Common commands:

Apply new pods (container):
kubectl -n UsedNamespace apply -f deployment.yaml

Show pods, pvc, pv:
kubectl -n UsedNamespace get pods
kubectl -n UsedNamespace get pvc
kubectl -n UsedNamespace get pv

Delete pods and volumens
kubectl -n UsedNamespace delete pod podname
kubectl -n UsedNamespace delete pvc pvcname
kubectl -n UsedNamespace delete pv pvname

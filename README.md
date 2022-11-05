# otobo-kubernetes
OTOBO repository for Kubernetes.
1. create namespace
2. create configmaps
3. create persistentvolumeclaims
4. create deployments
5. create services
6. create ingressroute
7. http://localhost/otobo/installer.pl
8. web and daemon should run on same node if using longhorn(Multiattach error)
9. disable redis in config file and set this in sysconfig.

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

# Set-K8s-Dashboard
SSH into Master Node

Create Dashboard
```sh
kubectl create -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.5.0/aio/deploy/recommended.yaml
```
By default, the service is only available internally to the cluster (ClusterIP) 
but changing to NodePort exposes the service to the outside.
```sh
kubectl edit service/kubernetes-dashboard -n kubernetes-dashboard
```
Get kubernetes-dashboard Pod name 
```sh
kubectl get pods --all-namespaces
```
Delete Pod by kubernetes-dashboard Pod name 
```sh
kubectl get pods --all-namespaces
```
Create serviceaccount as dashboard-admin-sa
```sh
kubectl create serviceaccount dashboard-admin-sa
kubectl create clusterrolebinding dashboard-admin-sa \
--clusterrole=cluster-admin --serviceaccount=default:dashboard-admin-sa
```
Get kubectl get secrets token name 
```sh
kubectl get secrets
```
Get kubectl get secrets token
```sh
kubectl describe secret dashboard-admin-sa-token-jh7bc
```
Get service port number
```sh
kubectl get svc --all-namespaces
```

open browerser 
```sh
https://masterIP:port
```








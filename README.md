# k8s/openshift-debuging
debugging steps for openshift


Cleaning Evicted pods from the cluster
```
kubectl get pods --all-namespaces | grep Evicted | awk '{print $2" --namespace="$1}' | xargs kubectl delete pod --grace-period=0 --force"
```

## lab:
```
kubectl get pods                         # list all running pods in current active namespace
kubectl get pods --all-namespaces        # list all running pods in all namespaces available
kubectl get pods -o wide                 # list all running pods in current active namespace wider output

kubectl describe pod <podname>              # detailed output about a pod in current namespace

kubectl logs my-pod                                 # dump pod logs (stdout)
kubectl logs -f my-pod                              # stream pod logs (stdout)

kubectl exec -it my-pod -- /bin/bash     # get interactive shell of the container in existing pod ( 1 container case )

kubectl expose pod nginx --target-port=80 --type=NodePort # expose pod as service within the cluster & outside of the cluster

kubectl delete pods <podname>                    # delete a pod in current active namespace
kubectl delete pods --all                        # delete all pods 
kubectl delete pod <pod-name> --grace-period=0 --force  # delete pod forcefully
```

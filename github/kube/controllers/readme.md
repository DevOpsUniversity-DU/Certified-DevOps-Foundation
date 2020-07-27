## Lab: Deployments
```
create a manifest file with Kind Deployment & use kubectl to create the object in k8s API Server.

kubectl create -f deployment-ex1.yml --record      # create deployment
kubectl apply -f deployment-ex1.yml  --record      # update the deployment 

kubectl get deploy                              # List all deployments in current active namespace
kubectl get deploy -n <namespace>               # List the deployments in <namespace>

kubectl describe deploy <deployment>                # inspect the deployment
kubectl scale --replicas=x deploy <deployment>      # Scale up/down deployment
kubectl delete deploy <deployment>                  # delete deployment & pod under it
```

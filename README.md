# kubernetes

 git config --global --list
 git config --global user.name 'DesiredUserNameHere'
 git config --global user.email 'DesiredUserNameHere'

 from credentials manager -> windows credentials -> remove git credential then login again

 # namespaces commands
kubectl get pods --namepace=dev

set default namespace

kubectl config set-context $(kubectl config current-context) --namespace=dev

if you changed the default context and want to see the actual defual then run kubectl get pods --namespace=default

kubectl get pods --all-namespaces

access service in different namespace 

service-y.namespace-b.svc.cluster.local


# imperative approach

create
kubectl run --image=nginx nginx
kubectl create deployment --image=nginx nginx
kubectl expose deployment nginx --port 80

update
kubectl edit deployment nginx
kubectl scale deployment nginx --replicas=5
kubectl set image deployment nginx nginx=nginx:1.18
kubectl create -f nginx.yaml
kubectl replace -f nginx.yaml
kubectl delete -f nginx.yaml 

# declarative 
create object
kubectl apply -f nginx.yaml

can apply all file at once
kubectl apply -f /path/to/config-files

update objects
kubectl apply -f nginx.yaml

kubectl get pods -n kube-system

# lables and sellectors
 kubectl get pods --selector app=app1
 
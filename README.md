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

 kubectl get pods --selector env=prod,tier=frontend,bu=finance

# replica sets
 kubectl get replicaset

# get all
 kubectl get all --selector key=value

# count
kubectl get pods | wc -l   ->this command count lines with headers so the right command would be

kubectl get pods --no-headers | wc -l

# taint and tolerence
taint is a color/spray tolerence is ability of pods to digest/tolerate that taint 
eg: if we paint/taint blue on one node and bydefault all pods are untolerent to blue and if we make some pods tolerent to blue then only those pods will be able to run/deploy on that node  

taint only restrict other pods to run on tainted node but paint on the pod does not restrict pod to run on a specific node
 


taint on nodes
paint on pods

kubectl describe node kubemaster | grep Taint
<!-- Taint: master:NoShedule -->


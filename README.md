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

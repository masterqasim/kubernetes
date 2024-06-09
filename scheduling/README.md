# taints-Node

kubectl taint nodes kay=value:taint-effect

taint-effect means (what happens to the pod that do not tolerate this taints)

NoSchedule
PreferNoSchedule
NoExecute ( new will not schedule on this node and existing will evicted )

kubectl taint node controlplane  node-role.kubernetes.io/control-plane:NoSchedule-
kubectl describe nodes node01 |grep Tain
kubectl run bee --image=nginx --dry-run=client -o yaml> bee.yaml

indendation after colon is must
eg
key: "example-key"


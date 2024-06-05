# taints-Node

kubectl taint nodes kay=value:taint-effect

taint-effect means (what happens to the pod that do not tolerate this taints)

NoSchedule
PreferNoSchedule
NoExecute ( new will not schedule on this node and existing will evicted )


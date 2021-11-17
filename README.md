# Kube

https://github.com/run-x/awesome-kubernetes

nice Kube cheat sheet

https://swissarmydevops.com/wp-content/uploads/2020/11/Kubernetes_Cheat_Sheet-2.pdf


Definitions
Let’s check out some terminology below:

Basic Objects
pod = container / set of containers + storage resources + unique IP + local options
service = abstraction layer on top of a set of ephemeral pods (think of this as the ‘face’ of a set of pods)
volume = sometimes-shared, persistent storage
namespace = virtual cluster on top of an underlying physical cluster

Service Types
clusterIP = exposes services only inside the cluster (default)
nodePort= exposes services at the specified port on all nodes (<node-ip>:<nodePort>)
loadBalancer = exposes the service with a cloud-provider’s load balancer.
externalName = this maps a service to endpoints completely outside of the cluster
  
Controllers
replicaSet = ensures a certain number of pods are running
deployment = declaratively manages a replicaSet
statefulSet = like a deployment, but for non-interchangeable (or stateful) underlying pods
daemonSet = manages pods that need to run on all/some nodes
job = manages a set of pods that run to completion and tracks the overall progress
  
Control Plane
master = entity responsible for managing cluster state. It consists of 3 major components:
kube-apiserver = exposes cluster control and state
kube-controller-manager = this is where the ‘brain’ of controllers live
kube-scheduler = matches resources to work
node = individual machines or VMs that make up the cluster. A node consists of:
kubelet = service that communicates with the master
kube-proxy = proxy for connecting to the cluster network
namespace -> virtual cluster on top of an underlying physical cluster

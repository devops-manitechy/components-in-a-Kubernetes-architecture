# Kubernetes Architecture Components

Kubernetes is a powerful container orchestration platform that manages containerized applications across a cluster of machines. Understanding its architecture components is crucial for effectively deploying and managing applications. Below are the key components of the Kubernetes architecture:

## Master Components

### API Server

The API Server exposes the Kubernetes API, allowing users to interact with the cluster. It serves as the front end for the Kubernetes control plane.

### Scheduler

The Scheduler watches for newly created pods with no assigned node and selects a node for them to run on based on resource availability and other constraints.

### etcd

etcd is a consistent and highly-available key-value store used as Kubernetes' backing store for all cluster data. It holds the state of the entire Kubernetes cluster.

### Controller Manager

The Controller Manager runs controller processes responsible for monitoring the state of the cluster and making changes to bring the actual state closer to the desired state. Examples of controllers include replication controller, endpoint controller, namespace controller, and more.

## Node Components

### Kubelet

Kubelet is an agent that runs on each node in the cluster. It ensures that containers are running in a pod by managing PodSpecs and ensuring the described containers are running and healthy.

### kube-proxy

kube-proxy maintains network rules on nodes, allowing network communication to your Pods from network sessions inside or outside of your cluster.

### Container Runtime

The Container Runtime is responsible for running containers. Kubernetes supports several container runtimes including Docker, containerd, and others. It's responsible for pulling the container image from a registry, unpacking the container, and running the application.



![image](https://github.com/devops-manitechy/components-in-a-Kubernetes-architecture/assets/70797344/f87cafcf-d705-42bd-aa0e-caff4ccb6dbc)


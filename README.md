# Master Components:

API Server: Exposes the Kubernetes API, which enables users to interact with the cluster. It serves as the front end for the Kubernetes control plane.

Scheduler: Watches for newly created pods with no assigned node, and selects a node for them to run on based on resource availability and other constraints.

etcd: A consistent and highly-available key-value store used as Kubernetes' backing store for all cluster data. It holds the state of the entire Kubernetes cluster.

Controller Manager: Runs controller processes, which are responsible for monitoring the state of the cluster and making changes to bring the actual state closer to the desired state. Examples of controllers include replication controller, endpoint controller, namespace controller, and more.


# Node Components:

Kubelet: An agent that runs on each node in the cluster. It makes sure that containers are running in a pod. It takes a set of PodSpecs that are provided through various mechanisms and ensures that the containers described in those PodSpecs are running and healthy.

kube-proxy: Maintains network rules on nodes. These network rules allow network communication to your Pods from network sessions inside or outside of your cluster.

Container Runtime: The software responsible for running containers. Kubernetes supports several container runtimes including Docker, containerd, and others. It's responsible for pulling the container image from a registry, unpacking the container, and running the application.

![image](https://github.com/devops-manitechy/components-in-a-Kubernetes-architecture/assets/70797344/f87cafcf-d705-42bd-aa0e-caff4ccb6dbc)


        +------------------------+
        |        Kubernetes      |
        |       Master Node      |
        +------------------------+
                 |
       +---------+-----------+
       |                     |
+------+--------------------+--------+
|     API Server         Scheduler   |
+-------------------------------------+
|                etcd                 |
+-------------------------------------+
|         Controller Manager          |
+-------------------------------------+
            |      |      |
  +---------+------+------+---------+
  |         |             |         |
Worker   Worker        Worker    Worker
Node 1   Node 2        Node 3    Node 4
+---+     +---+         +---+     +---+
|   |     |   |         |   |     |   |
| Kubelet|Kubelet|  Kubelet|Kubelet|
| kube-  | kube-  |  kube-  | kube-  |
| proxy  | proxy  |  proxy  | proxy  |
+-------+ +-------+ +-------+ +-------+
|   Container Runtime (e.g., Docker)  |
+-------------------------------------+


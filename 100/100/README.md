# 100 - Concepts


## Autoheal
Autoheal allows you to keep the nodes in your pool in a healthy state. When enabled, periodic checks are performed to ensure all your nodes are running properly.

## Autoscale
Autoscale allows your cluster to automatically scale up or down.

## Auto-upgrade
Auto-upgrade allows you to schedule a maintenance window for your cluster to be upgraded to a more recent version of Kubernetes. The upgrade process will occur within two hours from the time defined by you.

## Cluster
A cluster is a set of machines, called nodes, running containerized applications managed by Kubernetes. A cluster has several worker nodes and at least one control plane. Each cluster is built for High Availability with a redundancy on the control plane. Refer to the control plane concept for more information regarding the cluster’s limitations. Scaleway allows you to create two types of clusters: Kapsule, for clusters comprising Scaleway Instances, and Kosmos, for multi-cloud clusters.

## Container Network Interface (CNI)
CNI (Container Network Interface) is a Cloud Native Computing Foundation project
. It consists of a specification and libraries for writing plugins to configure network interfaces in Linux containers, along with a number of plugins.

## Container runtime
The container runtime is the software that is responsible for running containers.

## Control plane
The control plane manages the worker nodes and the pods in the cluster. In production environments, the control plane usually runs across multiple computers, and a cluster usually runs multiple nodes, providing fault-tolerance and high availability. Scaleway manages the control plane and associated Load Balancers. Consider the following when creating a control plane:

- A cluster belongs to one region.
- As the cluster’s control plane and Load Balancer are managed by Scaleway, it is not possible to access them directly or configure them individually.
- A cluster requires a minimum of one pool of worker machines to deploy Kubernetes resources. Note that pods must run on a worker node.

## Easy Deploy
The Easy Deploy feature allows you to pull images directly from Scaleway Container Registry, instantly deploying containerized applications in your Kubernetes Kapsule cluster. With only the basic options to set, you can use Kubernetes Kapsule without needing to manage your .yaml  manifests. Check out our documentation on creating containerized applications with the Easy Deploy feature for more information.

## Image pull secret
Image pull secrets are tokens that authorize Kubernetes to pull images from private container registries.

## Ingress
Ingress is an API object that manages external access to the services in a cluster, typically HTTPS. Ingress can provide load balancing, SSL termination, and name-based virtual hosting.

## Ingress controller
Kubernetes supports a high-level abstraction called Ingress, which allows simple host or URL-based HTTP routing. Ingress is a core concept (in beta) of Kubernetes, but is always implemented by a third-party proxy. These implementations are known as ingress controllers. An ingress controller is responsible for reading the Ingress Resource information and processing that data accordingly. Different ingress controllers have extended the specification in different ways to support additional use cases. For more information, see our dedicated how-to on deploying ingress controllers.

## KubeConfig
kubeconfig is a file provided by Scaleway when creating a Kubernetes cluster. It allows you to manage your cluster from your local computer by using kubectl.

## Kubectl
Kubectl is the command line interface for running commands against Kubernetes clusters. You can use kubectl to connect to and manage your clusters from the command line.

## Kubernetes
Kubernetes (K8s) is an open-source platform for managing containerized workloads and services. Google initially developed the project, which became publicly available in 2014.

## Kubernetes Kapsule
Kubernetes Kapsule provides a managed environment for you to create, configure, and run a cluster of pre-configured machines for containerized applications. It allows you to create Kubernetes
 clusters without the complexity of managing the infrastructure. Kubernetes Kapsule clusters are composed uniquely of Scaleway Instances. Read our documentation on how to create a Kubernetes Kapsule. To create clusters including Instances from external cloud providers, see Kubernetes Kosmos.

## Kubernetes Kosmos
Kubernetes Kosmos is the first-of-its-kind managed multi-cloud Kubernetes Engine. It allows the connection of Instances and servers from any Cloud provider to a single managed control plane hosted by Scaleway. Using Kubernetes in a multi-cloud cluster provides a high level of application redundancy by authorizing pod replication across different providers, regions, and Availability Zones. See our documentation to learn how to create a Kubernetes Kosmos cluster.

## Load Balancer
Load balancing efficiently distributes incoming network traffic across a group of backend servers. Scaleway manages the entire Load Balancer service, including traffic between API masters.

## Managed service
Scaleway Kapsule and Kosmos are managed Kubernetes services. Scaleway’s managed Kubernetes service abstracts away the complexities of managing and operating a Kubernetes cluster, enabling developers to focus on application development and deployment while ensuring a reliable and scalable environment for running containerized workloads. These services allow users to focus on deploying and running applications on Kubernetes without worrying about the underlying infrastructure and operational complexities.

For more information, refer to the managed Kubernetes service definition.

## Minikube
Minikube runs a single-node Kubernetes cluster inside a VM on your computer or cloud server for developing and testing applications. Minikube supports Kubernetes features such as:

- DNS
- NodePorts
- ConfigMaps and Secrets
- Dashboards
- Container Runtime: Docker, rkt, CRI-O and containerd
- Enabling CNI (Container Network Interface)
- Ingress

## Namespace
Namespaces are used in Kubernetes to divide the same cluster resources between multiple virtual users. Namespaces are intended for use in environments with many users spread across multiple teams or projects.

## Node
Kubernetes runs your workload by placing containers into pods to run on nodes. A node may be a virtual or physical machine, depending on the cluster. Each node is managed by the control plane and contains the services necessary to run pods.

## Pods
A pod is the smallest and simplest unit in the Kubernetes object model. Containers are not directly assigned to hosts in Kubernetes. Instead, one or multiple containers that are working closely together are bundled in a pod together, sharing a unique network address, storage resources and information on how to govern the containers.

## Pool
The Pool resource is a group of Scaleway Instances, organized by type (e.g., GP1-S, GP1-M). It represents the computing power of the cluster and contains the Kubernetes nodes, on which the containers run. Consider the following when creating a Pool:

- Containers require a minimum of one Instance in the Pool.
- A pool belongs to only one cluster, in the same region.

## ReplicaSet
The task of a ReplicaSet is to create and delete pods as needed to reach the desired status. A ReplicaSet contains:

- Information about the number of pods it can acquire
- Information about the number of pods it maintains
- A pod template, specifying the data of new pods to meet the number of replicas criteria. Each pod within a ReplicaSet can be identified via the metadata.ownerReference field, allowing the ReplicaSet to monitor each pod’s state.

## Services
A service is an abstraction that defines a logical group of pods that perform the same function, and a policy on how to access them. The service provides a stable endpoint (IP address) and acts as a Load Balancer by redirecting requests to the different pods in the service. The service abstraction allows the scaling out or replacement of dead pods without making changes to the configuration of an application. By default, services are only available using internally routable IP addresses, but can be exposed publicly. This can be done using the NodePort configuration, which opens a static port on each node’s external networking interface. Alternatively, it is also possible to use the load-balancer service, which creates an external Load Balancer at a cloud provider using Kubernetes load-balancer integration.

## System volume
The system volume is a read-only volume that stores essential files for the Kubernetes system, such as runtime binaries, configuration files, and certificates. It is managed by the node and kept separate from application data.

Depending on the type of node selected, we provide one or two types of volume.

- Local storage: your system is stored locally on the hypervisor of your node.
- Block Storage: your system is remotely stored on a centralized and resilient cluster.

As a general guideline, your system volume disk should have a capacity of at least 20 GB to ensure enough space to store the necessary system files and configurations.
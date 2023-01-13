# run-devops
Deploying .Net Microservices to AKS and Automating with  Azure DevOps
[![Build Status](https://dev.azure.com/hsharmaiet/shopping/_apis/build/status/shoppingclient-pipeline?branchName=main)](https://dev.azure.com/hsharmaiet/shopping/_build/latest?definitionId=4&branchName=main)
[![Build Status](https://dev.azure.com/hsharmaiet/shopping/_apis/build/status/shoppingapi-pipeline?branchName=main)](https://dev.azure.com/hsharmaiet/shopping/_build/latest?definitionId=3&branchName=main)
**About Kubernetes**
k8s Introduction https://www.youtube.com/watch?v=TlHvYWVUZyc
1. k8s is an open-source container orchestration platform.
2. It automates the deployment, scaling and management of containerized applications.
3. It can be traced back to Google's internal container ocrahstration system Borg, which managed the deployment of thousands of applications within Google.
4. In 2014, Google open-sourced a version of Borg. That is kubernetes.
5. A k8s cluster is a set of machines called nodes, that are used to run containerized applications.
6. There are 2 core pieces in a k8s cluster.
7. i) Control Plane: It is responsible for managing the state of the cluster. In production environments the control plane usually runs on multiple nodes that span across several data center zones.   
8. ii) Worker nodes: These nodes run the containerized appliaction workloads. The containerized applications run in a Pod. Pods are the smallest deployable units in k8s. A pod hosts one or more containers and provides shared storage and networking for those containers. Pods are created and managed by k8s control plne.
9. Control Plane (dive deep): It consists of a number of core components.
   API Server: is the primary interface b/w the contorl plane and the rest or the cluster. It exposes a RESTful API that allows clients to interact with the control and submit requests to manage the cluster.
   etcd: is a distributed key value store. It stores the cluster's perisstent state. It is used by the API server and other componests of the control plane to store and retrieve information about the cluster.
   Scheduler: is responsible for scheduling pods into the worker nodes in the cluster. It uses information about the resources required by the pods and the available resourece on the worker nodes to make placement decisions.
   Controller manager: is responsible for running controllers tht manage the state of the cluster. ex, replication controller - which ensures that the desired number of replicas of a pod are running, and the deployment controller- which manages the rolling update and rollback of deployments.
10. Worker nodes (deep dive): The core components of k8s that run on the worker nodes include kubelet, contaner runtime, and kube proxy. 
  The kubelet: is a daemon that runs on each worker node. It is responsible for communicating wiht the control plane. It receives instructions from the control plane about which pods to run the node, and ensures that the desired state of the pods is maintained.
  Container runtime: runs the containers on the workder nodes. It is reponsible for pulling the container images from a registry, starting and stopping the containers,and managing the conatainer's resources.
  kube-proxy: is a network proxy that runs on each worker node. Ir is responsible for routing traffic to the correct pods. It also proved load balancing for the pods and ensures that traffic is distributed evenly across the pods.

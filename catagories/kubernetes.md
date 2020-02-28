# Kubernetes

<a name="kubernetes-beginner"></a>

<details>
<summary>What is Kubernetes? What use cases is it good for?</summary><br><b>

Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications.

To understand what Kubernetes is good for, let's look at some examples:

- You would like to run a certain application in a container on multiple different locations. Sure, if it's 2-3 servers/locations, you can do it by yourself but it can be challenging to scale. Also, running them is not only running the container but also react on different events.

- Performing updates and changes across hundreds of containers

- Handle cases where the current load requires to scale up (or down)
  </b></details>

<details>
<summary>Describe the architecture of Kubernetes</summary><br><b>
</b></details>

<details>
<summary>What is a Kubernetes Cluster?</summary><br><b>

A cluster consists of a Master (which coordinates the cluster) and Nodes where the applications are running.
</b></details>

<details>
<summary>What the Master is responsible for?</summary><br><b>

The master coordinates all the workflows in the cluster:

- Scheduling applications
- Managing desired state
- Rolling out new updates
  </b></details>

<details>
<summary>What is a Node?</summary><br><b>

A node is a virtual machine or a physical server that serves as a worker for running the applications.
It's recommended to have at least 3 nodes in Kubernetes production environment.
</b></details>

<details>
<summary>Explain what is Kubelet</summary><br><b>

Kubelet is an agent running on each node and responsible for node communication with the master.
</b></details>

<details>
<summary>What is Minikube?</summary><br><b>

Minikube is a lightweight Kubernetes implementation. It create a local virtual machine and deploys a simple (single node) cluster.
</b></details>

<details>
<summary>Explain what is a Kubernetes pod</summary><br><b>
</b></details>

<details>
<summary>True or False? A pod can manage multiple containers</summary><br><b>
</b></details>

<details>
<summary>How do you monitor your Kubernetes?</summary><br><b>
</b></details>

<details>
<summary>You suspect one of the pods is having issues, what do you do?</summary><br><b>

Start by inspecting the pods status. we can use the command `kubectl get pods` (--all-namespaces for pods in system namespace)<br>

If we see "Error" status, we can keep debugging by running the command `kubectl describe pod [name]`. In case we still don't see anything useful we can try stern for log tailing.<br>

In case we find out there was a temporary issue with the pod or the system, we can try restarting the pod with the following `kubectl scale deployment [name] --replicas=0`<br>

Setting the replicas to 0 will shut down the process. Now start it with `kubectl scale deployment [name] --replicas=1`
</b></details>

<details>
<summary>What the Kubernetes Scheduler does?</summary><br><b>
</b></details>

<details>
<summary>What happens to running pods if if you stop Kubelet on the worker nodes?</summary><br><b>
</b></details>

<details>
<summary>Describe how roll-back works</summary><br><b>
</b></details>

#### Kubernetes Commands

<details>
<summary>What is kubectl?</summary><br><b>
</b></details>

<details>
<summary>How do you:

- Check the cluster status?
- Check the status of the nodes?</summary><br><b>
  </b></details>

<details>
<summary>What the following commands do?

- kubectl get nodes
- kubectl </summary><br><b>
  </b></details>

<details>
<summary>What is kubconfig? What do you use it for?</summary><br><b>
</b></details>

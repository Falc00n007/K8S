<img src="https://kubernetes.io/images/nav_logo2.svg" width="210" style="margin-right: 10px;">

## Upon its initial release, Kubernetes lacked a vital element:
A means to identify the operational servers. This created an array of challenges within the community, 
encompassing the inability to allocate applications to specific nodes and prevent resource overflow onto other nodes.
To address this predicament, the Kubernetes team collaborated with Google to develop a resolution known as "**kubectl get nodes,**"
which serves as the fundamental component. In the following discourse, you will gain insight into its functionality and explore
practical illustrations of its utilization.

## What Is **“kubectl get nodes”?**
The result of employing this command will display comprehensive details regarding your Kubernetes nodes.
For further information regarding all the nodes in plain text layout, you can opt for the command **kubectl get nodes -o-wide**.
This approach not only supplies additional details but also indicates the active IP addresses within your cluster.

The utilization of the --wide flag offers numerous advantages. It presents a broader range of information and grants a deeper 
understanding of the operations taking place within your cluster. If your objective is to resolve any concerns within your cluster,
it is advisable to use this option instead of solely relying on **-o name**.

**“Kubectl get nodes”** is a command to retrieve information about nodes in aKubernetes cluster. This information includes the
node’s name, role, and status. The command can also get the list of nodes in a cluster and specific information about a node. 
You can use it like this:

```
kubectl get nodes
```

List Master nodes
```
kubectl get nodes --selector='node-role.kubernetes.io/master'
```
List worker nodes
```
kubectl get nodes --selector='!node-role.kubernetes.io/master'
```
The **"Kubectl get nodes"** command provides essential information, including historical deployment data. For instance,
if you encounter a rolling upgrade with twenty images on your node, you can access this information from the time 
series that spans five months. Additionally, it furnishes details about your services' state such as node selector 
and active endpoints, which can be incredibly useful for debugging purposes, enabling you to identify the cause when
things don't go as expected.

**Here are examples of what you can obtain using the command:**

# The node’s name:
- The name of the node, displayed as the "Name" field in the node list and output when specifying the "--output" flag.

# The node’s annotations:
- Annotations associated with the node, which offer documentation specific to that node. If you're familiar with the 
**"kubectl edit"** command, you'll find it easy to apply annotations. 
Using **"kubectl get nodes,"** you can view the annotations applied to nodes in your cluster.

# The node’s labels:
- Labels assigned to the node, listed under **"Labels."** You can also filter nodes based on a specific label by
running **"kubectl get nodes** **--label=<label>."**

# The health of a node:
- The node's health, which is crucial to determine if it has been unhealthy for a specified period. To check the 
node's health, execute the following command. If you receive a **"Status:"** value of **"Up,"** it indicates that
everything is functioning properly.

```
kubectl get nodes -o=custom-columns=NAME:.metadata.name,STATUS:.status | grep Up
```


# The IP address of the nodes:

To determine the IP addresses assigned to your nodes, you can utilize the **"kubectl get nodes"** command.
Follow the given command:

```
kubectl get nodes -o=custom-columns=NAME:,IP
```

# Where is "kubectl get nodes" not applicable?

***"Kubectl get nodes"** is a command used to fetch information from a local Kubernetes cluster.
It provides details of all the pods, deployments, services, and ReplicationControllers. However,
it cannot be used to access resources from remote clusters, it only provides information about
containers on the local machine.

Additionally, **"kubectl get nodes"** cannot be used to specifically retrieve a certain pod within
the cluster. The command's output categorizes pods under Labels and Compute Resources, organized by namespace.

# Summary:

By running the **"kubectl get nodes"** command, you can gather information about the connected nodes in your
cluster. It allows you to assess their health, applied labels, and uptime duration. This command provides a
comprehensive overview of all running services, highlighting any resource-intensive or redundant ones.
It is recommended to periodically check this command (at least once every few weeks) to ensure the smooth
functioning of your cluster.

The popularity of Kubernetes has led to the creation of several powerful tools that seamlessly integrate 
with the platform. One such tool is Loft, a control plane that enhances existing clusters by leveraging 
the **self-service capabilities** of the platform. Loft facilitates **multi-tenancy** and effectively manages
various aspects of your cluster.

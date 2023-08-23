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

Here's a table of frequently used `kubectl` commands in Kubernetes:

| **Command**                              | **Description**                                               |
|------------------------------------------|---------------------------------------------------------------|
| `kubectl get nodes`                      | List all nodes in the cluster                                 |
| `kubectl get pods`                       | List all pods in the current namespace                        |
| `kubectl get services`                   | List all services in the current namespace                    |
| `kubectl get deployments`                | List all deployments in the current namespace                 |
| `kubectl get namespaces`                 | List all namespaces                                           |
| `kubectl describe pod <pod-name>`        | Show detailed information about a specific pod                |
| `kubectl describe service <service-name>`| Show detailed information about a specific service            |
| `kubectl describe deployment <deploy-name>` | Show detailed information about a specific deployment       |
| `kubectl create -f <file.yaml>`          | Create a resource from a YAML or JSON file                     |
| `kubectl apply -f <file.yaml>`           | Apply a configuration change to a resource from a YAML/JSON file|
| `kubectl delete -f <file.yaml>`          | Delete a resource defined in a YAML or JSON file               |
| `kubectl logs <pod-name>`                | View logs for a specific pod                                   |
| `kubectl exec -it <pod-name> -- /bin/bash`|Execute a command in a running pod (e.g., start a bash session) |
| `kubectl scale deployment <deploy-name> --replicas=<num>` | Scale the number of replicas in a deployment   |
| `kubectl rollout status deployment/<deploy-name>` | Check the status of a deployment rollout               |
| `kubectl rollout history deployment/<deploy-name>` | View the rollout history of a deployment              |
| `kubectl port-forward <pod-name> <local-port>:<remote-port>`| Forward a port from the local machine to a pod |
| `kubectl config get-contexts`            | List all contexts in the kubeconfig file                       |
| `kubectl config use-context <context-name>` | Set the current context to a specified context               |
| `kubectl apply -k <directory>`           | Apply a Kubernetes manifest using Kustomize from a directory   |
| `kubectl top nodes`                      | Display resource (CPU/memory) usage for nodes                  |
| `kubectl top pods`                       | Display resource (CPU/memory) usage for pods                   |

This table covers the most common commands used for managing and troubleshooting Kubernetes clusters.

Here's a breakdown of Kubernetes commands categorized into "First Aid" (frequently used for basic troubleshooting and inspection) 
"Second Level Treatment" (commands used for deeper debugging and analysis):

### First Aid Commands

These commands help with basic checks and quick insights:

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `kubectl get ns`                                    | List all namespaces                                         |
| `kubectl get pods`                                 | List all pods in the current namespace                      |
| `kubectl get pods -n <namespace>`                   | List all pods in a specific namespace                       |
| `kubectl get pods -o wide`                          | List all pods with additional details (like node they are on) |
| `kubectl get svc`                                   | List all services in the current namespace                  |
| `kubectl get svc -n <namespace>`                     | List all services in a specific namespace                   |
| `kubectl describe pod <pod-name>`                    | Show detailed information about a specific pod             |
| `kubectl logs <pod-name>`                            | Show logs for a specific pod                                |
| `kubectl logs -f <pod-name>`                         | Follow logs for a specific pod                              |
| `kubectl describe pod <pod-name> -n <namespace>`     | Show detailed information about a specific pod in a namespace |
| `kubectl exec -it <pod-name> -- /bin/bash`          | Start a bash session in a running pod                       |
| `kubectl get events`                               | List recent events in the cluster                           |
| `kubectl top pods`                                 | Show CPU and memory usage for pods                          |

### Second Level Treatment Commands

These commands provide more detailed diagnostics and troubleshooting:

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `kubectl describe pod <pod-name>`                    | Detailed information about a specific pod, including events and resource usage |
| `kubectl describe pod <pod-name> -n <namespace>`     | Detailed information about a pod in a specific namespace   |
| `kubectl get pod <pod-name> -o yaml`                 | View the YAML configuration of a specific pod               |
| `kubectl get pod <pod-name> -o json`                 | View the JSON configuration of a specific pod               |
| `kubectl logs <pod-name> -c <container-name>`        | View logs from a specific container within a pod            |
| `kubectl logs <pod-name> --previous`                 | View logs from the previous instance of a container (if it has crashed) |
| `kubectl describe service <service-name>`            | Detailed information about a specific service               |
| `kubectl describe node <node-name>`                  | Detailed information about a specific node                  |
| `kubectl top nodes`                                 | Show CPU and memory usage for nodes                         |
| `kubectl get events --sort-by=.metadata.creationTimestamp` | List events sorted by creation timestamp for better insight |
| `kubectl debug pod <pod-name> --image=<debug-image>` | Create a debugging container in the pod using a specified image |

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `kubectl get pod <pod-name> -o custom-columns=NAME:.metadata.name,STATUS:.status.phase,RESTARTS:.status.containerStatuses[0].restartCount` | Get custom columns for a specific pod’s status and restart count |

These commands should help you with both initial diagnostics and deeper troubleshooting when working with Kubernetes pods and other resources.




If you are working with AWS EKS (Elastic Kubernetes Service), many `kubectl` commands remain the same, but there are a few additional AWS-specific commands and considerations to be aware of. Below is a list of commonly used commands for managing and troubleshooting an EKS cluster, divided into "First Aid" and "Second Level Treatment."

### First Aid Commands

These commands help with basic checks and quick insights:

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `kubectl get ns`                                    | List all namespaces                                         |
| `kubectl get pods`                                 | List all pods in the current namespace                      |
| `kubectl get pods -n <namespace>`                   | List all pods in a specific namespace                       |
| `kubectl get pods -o wide`                          | List all pods with additional details (like node they are on) |
| `kubectl get svc`                                   | List all services in the current namespace                  |
| `kubectl get svc -n <namespace>`                     | List all services in a specific namespace                   |
| `kubectl describe pod <pod-name>`                    | Show detailed information about a specific pod             |
| `kubectl logs <pod-name>`                            | Show logs for a specific pod                                |
| `kubectl logs -f <pod-name>`                         | Follow logs for a specific pod                              |
| `kubectl describe pod <pod-name> -n <namespace>`     | Show detailed information about a specific pod in a namespace |
| `kubectl exec -it <pod-name> -- /bin/bash`          | Start a bash session in a running pod                       |
| `kubectl get events`                               | List recent events in the cluster                           |
| `kubectl top pods`                                 | Show CPU and memory usage for pods                          |
| `aws eks update-kubeconfig --name <cluster-name>`   | Update kubeconfig for the EKS cluster                       |
| `aws eks list-clusters`                             | List all EKS clusters                                      |

### Second Level Treatment Commands

These commands provide more detailed diagnostics and troubleshooting:

| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `kubectl describe pod <pod-name>`                    | Detailed information about a specific pod, including events and resource usage |
| `kubectl describe pod <pod-name> -n <namespace>`     | Detailed information about a pod in a specific namespace    |
| `kubectl get pod <pod-name> -o yaml`                 | View the YAML configuration of a specific pod               |
| `kubectl get pod <pod-name> -o json`                 | View the JSON configuration of a specific pod               |
| `kubectl logs <pod-name> -c <container-name>`        | View logs from a specific container within a pod            |
| `kubectl logs <pod-name> --previous`                 | View logs from the previous instance of a container (if it has crashed) |
| `kubectl describe service <service-name>`            | Detailed information about a specific service               |
| `kubectl describe node <node-name>`                  | Detailed information about a specific node                  |
| `kubectl top nodes`                                  | Show CPU and memory usage for nodes                         |
| `kubectl get events --sort-by=.metadata.creationTimestamp` | List events sorted by creation timestamp for better insight |
| `kubectl debug pod <pod-name> --image=<debug-image>` | Create a debugging container in the pod using a specified image |
| `aws eks describe-cluster --name <cluster-name>`    | Get details about a specific EKS cluster                    |
| `aws eks list-nodegroups --cluster-name <cluster-name>` | List all node groups in a specific EKS cluster               |
| `aws eks get-token --cluster-name <cluster-name>`    | Get a token to authenticate to the EKS cluster                |


| **Command**                                          | **Description**                                              |
|------------------------------------------------------|--------------------------------------------------------------|
| `kubectl get pod <pod-name> -o custom-columns=NAME:.metadata.name,STATUS:.status.phase,RESTARTS:.status.containerStatuses[0].restartCount` | Get custom columns for a specific pod’s status and restart count |
| `aws eks describe-nodegroup --cluster-name <cluster-name> --nodegroup-name <nodegroup-name>` | Describe a specific node group in an EKS cluster |


These commands cover basic and advanced operations you might need to perform when managing and troubleshooting an AWS EKS cluster.

-----


When working with AWS EKS, it's common to have LoadBalancers associated with your services. Here are some additional commands and tools that can help you manage and troubleshoot LoadBalancers, along with the EKS cluster:

### EKS LoadBalancer Management Commands

#### **AWS CLI Commands for LoadBalancers**

| **Command**                                           | **Description**                                                |
|-------------------------------------------------------|----------------------------------------------------------------|
| `aws elb describe-load-balancers`                     | List all Classic LoadBalancers (ELB)                           |
| `aws elb describe-load-balancers --load-balancer-names <name>` | Get details for a specific Classic LoadBalancer (ELB)          |
| `aws elbv2 describe-load-balancers`                   | List all Application LoadBalancers (ALB) and Network LoadBalancers (NLB) |
| `aws elbv2 describe-load-balancers --load-balancer-arns <arn>` | Get details for a specific Application or Network LoadBalancer |
| `aws elbv2 describe-target-groups`                    | List all target groups                                       |
| `aws elbv2 describe-target-groups --target-group-arns <arn>` | Get details for a specific target group                      |
| `aws elbv2 describe-listeners --load-balancer-arn <arn>` | List all listeners for a specific LoadBalancer               |
| `aws elbv2 describe-listeners --listener-arn <arn>`   | Get details for a specific listener                          |
| `aws elbv2 describe-rules --listener-arn <arn>`       | List all rules for a specific listener                       |
| `aws elbv2 describe-rules --rule-arn <arn>`           | Get details for a specific rule                              |

#### **kubectl Commands for LoadBalancer Services**

| **Command**                                             | **Description**                                              |
|---------------------------------------------------------|--------------------------------------------------------------|
| `kubectl get svc`                                     | List all services and their associated LoadBalancers        |
| `kubectl get svc -n <namespace>`                       | List all services in a specific namespace                   |
| `kubectl describe svc <service-name>`                  | Show detailed information about a specific service, including LoadBalancer details |
| `kubectl describe svc <service-name> -n <namespace>`   | Show detailed information about a service in a specific namespace |

### Additional Tips for Troubleshooting LoadBalancers

1. **Check Service Status**:
   - Ensure that the service type is `LoadBalancer` and that it has an external IP assigned.
   - Example: `kubectl get svc <service-name> -o wide`

2. **Inspect LoadBalancer Details**:
   - Use the AWS Management Console or CLI to get detailed information about the LoadBalancer, its listeners, and associated target groups.

3. **Verify Target Health**:
   - For Application LoadBalancers (ALB) and Network LoadBalancers (NLB), check the health of targets to ensure they are responding correctly.
   - Example CLI command: `aws elbv2 describe-target-health --target-group-arn <target-group-arn>`

4. **Logs and Metrics**:
   - Check CloudWatch Logs and Metrics for insights into LoadBalancer performance and errors.
   - You can view and set up alerts for metrics such as request count, error rate, and latency.

5. **Update kubeconfig**:
   - Ensure that your `kubeconfig` is up to date with the EKS cluster context to properly interact with Kubernetes resources.
   - Example CLI command: `aws eks update-kubeconfig --name <cluster-name>`

By using these commands and tips, you should be able to manage and troubleshoot LoadBalancers associated with your EKS cluster effectively.

To switch namespaces in Kubernetes, you have a couple of options depending on whether you want to change the namespace for a single command or for all subsequent commands.

### Option 1: Switch Namespace for a Single Command

You can specify the namespace directly in the `kubectl` command using the `-n` or `--namespace` flag. For example:

- **List pods in a specific namespace:**
  ```bash
  kubectl get pods -n <namespace>
  ```

- **Describe a specific pod in a specific namespace:**
  ```bash
  kubectl describe pod <pod-name> -n <namespace>
  ```

### Option 2: Change the Default Namespace for the Current Context

If you want to switch to a different namespace for all subsequent `kubectl` commands in your current context, you can update your `kubectl` configuration to set a new default namespace. This avoids the need to specify the namespace in each command.

- **Set a default namespace for the current context:**
  ```bash
  kubectl config set-context --current --namespace=<namespace>
  ```

  This command updates the context in your kubeconfig file to use the specified namespace by default.

- **Verify the current context and namespace:**
  ```bash
  kubectl config view --minify | grep namespace:
  ```

### Example Workflow

1. **Check Current Namespace:**
   ```bash
   kubectl config view --minify | grep namespace:
   ```

2. **Switch Namespace for All Commands:**
   ```bash
   kubectl config set-context --current --namespace=my-new-namespace
   ```

3. **Verify Namespace Change:**
   ```bash
   kubectl config view --minify | grep namespace:
   ```

4. **Run Commands in New Namespace:**
   ```bash
   kubectl get pods
   kubectl get services
   ```

5. **Switch Back to Original Namespace (if needed):**
   ```bash
   kubectl config set-context --current --namespace=default
   ```

These methods allow you to either focus on a specific namespace temporarily or permanently change the default namespace for your kubectl commands.



Below is a list of useful AWS CLI commands for debugging AWS EKS clusters, 
categorized into "First Level" and "Second Level" steps for troubleshooting.

### First Level Debugging Commands

These commands help with basic checks and initial diagnostics:

| **Command**                                          | **Description**                                                |
|------------------------------------------------------|----------------------------------------------------------------|
| `aws eks list-clusters`                             | List all EKS clusters in the account                          |
| `aws eks describe-cluster --name <cluster-name>`    | Get details about a specific EKS cluster                      |
| `aws eks update-kubeconfig --name <cluster-name>`   | Update kubeconfig file to use the specified EKS cluster        |
| `aws eks list-nodegroups --cluster-name <cluster-name>` | List all node groups in a specific EKS cluster                 |
| `aws eks describe-nodegroup --cluster-name <cluster-name> --nodegroup-name <nodegroup-name>` | Get details about a specific node group in an EKS cluster      |
| `aws elbv2 describe-load-balancers`                  | List all Application and Network LoadBalancers (ALB/NLB)       |
| `aws elbv2 describe-target-groups`                   | List all target groups associated with ALBs and NLBs           |
| `aws elbv2 describe-target-health --target-group-arn <target-group-arn>` | Get health status of targets in a specific target group       |
| `aws cloudwatch describe-alarms`                     | List CloudWatch alarms that might be set up for the cluster    |
| `aws ec2 describe-instances`                        | List EC2 instances and their statuses (useful for node debugging) |

### Second Level Debugging Commands

These commands provide deeper insights and more detailed troubleshooting:

| **Command**                                          | **Description**                                                |
|------------------------------------------------------|----------------------------------------------------------------|
| `aws eks describe-cluster --name <cluster-name>`    | Detailed information about a cluster's configuration, including VPC, subnets, and security groups |
| `aws eks describe-nodegroup --cluster-name <cluster-name> --nodegroup-name <nodegroup-name>` | Detailed information about a node group, including scaling activities and health checks |
| `aws eks list-fargate-profiles --cluster-name <cluster-name>` | List Fargate profiles for the specified EKS cluster            |
| `aws eks describe-fargate-profile --cluster-name <cluster-name> --fargate-profile-name <profile-name>` | Get details about a specific Fargate profile                   |
| `aws elbv2 describe-load-balancers --load-balancer-arns <arn>` | Detailed information about a specific LoadBalancer             |
| `aws elbv2 describe-listeners --load-balancer-arn <arn>` | List listeners associated with a specific LoadBalancer          |
| `aws elbv2 describe-rules --listener-arn <arn>`       | Detailed information about rules for a specific LoadBalancer listener |
| `aws cloudwatch get-metric-data --metric-name <metric-name> --namespace <namespace>` | Retrieve specific metric data from CloudWatch                   |
| `aws ec2 describe-instance-status --instance-ids <instance-ids>` | Detailed status of EC2 instances, including system and instance status checks |
| `aws ec2 describe-security-groups --group-ids <security-group-ids>` | Detailed information about security groups associated with the EKS cluster |

These commands should help you with both initial diagnostics and more in-depth troubleshooting of AWS EKS clusters and related AWS resources.

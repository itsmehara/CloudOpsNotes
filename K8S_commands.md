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

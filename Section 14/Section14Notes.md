# Kubernetes Architecture 
- Kube or K8s are short forms
- Kubectl: CLI to manage Kube and manage the apps
- Node means the same which is a single server
- Needs it's own engine which is Kubelet the nodes will require this
- Need odd number of master nodes(also known as Control plane which is containers that manage the network )
- Series of containers, CLI's, and configurations

# Kubernetes Container Abstractions
- Pod: One or more containers running together on one Node
- Controller: For updating pods and other objects
- Service: network endpoint to connect to a pod when accessing a set of pods

# Kubernetes Run, Create, and Apply
- "kubectl run": Single pod is created 
- "kubectl create": Similar to creating in Swarm
- "kubectl apply": Mostly YAML differences to the environment 
- Check with "kubectl version" if it's working or not
- Always have to give a name to the pod no random names like Docker
- "kubectl run my-nginx --image nginx": pod/mg-nginx created does not mean it's running 
- Unlikely to use this in production until or unless you are trying to test something 
- "kubectl get pods": To list all of the pods
- "kubectl get all": Also lists the services and pods 
- Pods provide a layer of abstraction an idea of resource type
- "kubectl create deployment my-nginx --image nginx": For production mostly 
- Can still call this my-nginx since it's a different resource 
- It shows it's created but does not mean it's running always
- Deployment creates a ReplicaSet(for each new deployment type) and then pods 

# Scaling ReplicaSets
- "kubectl scale deploy {name of resource} --replicas 2
- deploy = deployment = deployments
- It changes the number of pods in ReplicaSet 

# Inspecting Kubernetes Objects
- "kubectl logs deploy/my-nginx": Will show the logs, only by default will pull one pods 
- "kubectl describe pod/my-nginx-xxxx-yyyy": Will show information about a specific pod
- "kubectl delete pod/my-nginx-xxxx-yyyy": Remove the pod
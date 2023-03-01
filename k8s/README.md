# hello 
kubernetes


Comman command:
- To see all the obejects in the kubernetes cluster:
kubectl get all


1. Pod
- For creating new pod :
kubectl run nginx --image nginx --dry-run=client -o yaml > test.yaml

- To see more information about pods
kubectl get pods -o wide

2. ReplicationController: 
- It is the old method
- It has apiVersion: v1 

3. ReplicaSet:
- It is new method
- It has apiVersion: apps/v1
- There are many pods are running in the node then in replicaSet we have "Labels and Selectors" They are help to identify specific pods.
- for scaling the replicaSet , change the number of replicas according to your requirement .

commands:
kubectl replace -f rs.yaml
or
kubectl scale --replicaset=6 -f rs.yaml
or
kubectl scale --replicaset=6 replicaset myreplicaset
or
kubectl edit replicaset myrepliaset

4. Deployment
- It is the kubernetes object same as replicaset
- apiVersion: apps/v1
- kind: Deployment

5. Namespace
- apiVersion: v1
- kind: Nmaespace
- we can permanently set the namespace by this command:

kubectl config set-context $(kubectl config current-context) --namespace=dev

- we can see all the pods accross all the namespaces by this command:

kubectl get pods --all-namespaces
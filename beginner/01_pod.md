Get list pod:
```
kubectl get pods
```
Get pods with wide output:
```
kubectl get pods -o wide
kubectl get pods --output=wide
```
View pod detail:
```
kubectl describe pod <pod_name>
```
To run a pod with specific imame:
```
kubectl run <pod name> --image=<image name> 
```
To run a yaml file:
```
kubectl create -f <file name>
```

Here is the pod definition yaml file:
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: myapp
  labels:
    app: myapp
spec:
  containers:
  - name: nginx
    image: nginx
```
To create a pod, run and output with yaml file:
```
kubectl run <pod name> --image=<image name> --dry-run=client -o yaml
```
=> this will be create `<pod name>.yaml` file
To apply change pod yaml file:
```
kubectl apply -f <file name>
```
To delete a pod:
```
kubectl delete pod <pod name>
```

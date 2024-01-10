Here is the example of deployment yaml file
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: frontend
  labels:
    app: mywebsite
    tier: frontend
spec:
  replicas: 4
  template:
    metadata:
      name: myapp-pod
      labels:
        app: myapp
    spec:
      containers:
        - name: nginx
          image: nginx
  selector:
    matchLabels:
      app: myapp
```
To create deployment from yaml file
```
kubectl create -f <file name>
```
To get deployments
```
kubectl get deployments
```
To get all the objects created at once:
```
kubectl get all
```
-----------------------------------------------------
Update and rollback

To update image of deployment:
```shell
kubectl set image <deployment name> <container name>=<new image name>
# Example:
kubectl set image deployment/myapp-deployment nginx-container=nginx:1.9.1
```
To rollback the deployment
```shell
kubectl rollout undo <deployment name>
```
To show status and history of rolling out deployment:
```shell
kubectl rollout status <deployment name>
kubectl rollout history <deployment name>
```

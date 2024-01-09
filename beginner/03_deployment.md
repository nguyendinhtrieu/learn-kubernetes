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

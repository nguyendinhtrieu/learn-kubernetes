#### ReplicationController is older technology that is being replaced by ReplicaSet.

#### Here the sample of ReplicaSet yaml file:
```yaml
apiVersion: apps/v1
kind: ReplicaSet
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
#### To replace replicaSet when changing yaml file:
```
kubectl replace -f <replicaSet file>
```
#### To update replicaSet by running kubectl scale command:
```
kubectl scale --replicas=<number of replicas> -f <replicaSet file>
kubectl scale --replicas=<number of replicas> replicaset <replicaSet name>
```
#### To get replicaSet
```
kubectl get replicaset
```
#### To describe replicaSet
```
kubectl describe replicaset <replicaSet name>
```
#### To directly edit existing replicaSet configuration in Kubernetes
```
kubectl edit replicaset <replicaSet name>
```
=> Then carefully edit the file and save
#### To delete replicaSet
```
kubectl delete replicaset <replicaSet name>
```
=> This will also deletes all underlying pods

Here is the example of service definition:
```yaml
apiVersion: v1
kind: Service
metadata:
  name: image-processing
  labels:
    app: myapp
spec:
  ports:
  - port: 80
    targetPort: 8080
    nodePort: 30001      #range: 30000 ~ 32747
  type: NodePort         # or using ClusterIP for accessing only on cluster (not access from outside)
  selector:
    tier: backend
```
To get services:
```shell
kubectl get services
```
To get the url of the service:
```shell
> minikube service <service name> --url
http://192.168.99.101:30001
```

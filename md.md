```yaml
apiVersion: v1
kind: Pod
metadata:
  name: example-pod
  labels:
    app: example-app
spec:
  containers:
  - name: example-container
    image: nginx
    ports:
    - containerPort: 80
```
text
```yaml
apiVersion: v1
kind: Service
metadata:
  name:  example-service
spec:
  selector:
    app:  example-app
  type:  NodePort
  ports:
    - name:  http
      port:  80
      nodePort: 30001
```
```yaml
apiVersion: v1
kind: Service
metadata:
  name:  example-service
spec:
  selector:
    app:  example-app
  type:  NodePort
  ports:
    - name:  http
      port:  80
      nodePort: 30001
```
```bash
kubectl apply -f <PATH>
```
```bash
kubectl get pods
```
```bash
ip addr
```
```
http://<IP_ADDRESS>:30001
```
```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: example-replicaset
spec:
  replicas: 3
  selector:
    matchLabels:
      app: example-app
  template:
    metadata:
      labels:
        app: example-app
    spec:
      containers:
      - name: example-container
        image: nginx:latest
        ports:
        - containerPort: 80
```
```bash
kubectl get replicasets
```
```bash
kubectl get pods
```
```bash
kubectl delete pods <POD_NAME>
```
```bash
kubectl scale --replicas 5 replicaset example-replicaset
```
```bash
kubectl delete replicasets example-replicaset
```
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: example-deployment
spec:
  selector:
    matchLabels:
      app: example-app
  replicas: 3
  template:
    metadata:
      labels:
        app: example-app
    spec:
      containers:
        - name: example-container
          image: nginx
          ports:
            - containerPort: 80
```
```bash
kubectl get deploy
```
```bash
kubectl get replicasets
```
```bash
kubectl get pods
```
```bash
kubectl get replicasets
```
```bash
kubectl get pods
```

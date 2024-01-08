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

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

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
```bash
curl -sfL https://get.k3s.io | sh -
```
```bash
sudo cat /var/lib/rancher/k3s/server/node-token
```
```bash
curl -sfL https://get.k3s.io | K3S_URL=https://<MASTER_NODE_IP>:6443 K3S_TOKEN=<TOKEN> sh -
```
```bash
sudo k3s kubectl get nodes
```
```yaml
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUJkakNDQVIyZ0F3SUJBZ0lCQURBS0JnZ3Foa2pPUFFRREFqQWpNU0V3SHdZRFZRUUREQmhyTTNNdGMyVnkKZG1WeUxXTmhRREUzTURNNU9ERTVOekF3SGhjTk1qTXhNak14TURBeE9UTXdXaGNOTXpNeE1qSTRNREF4T1RNdwpXakFqTVNFd0h3WURWUVFEREJock0zTXRjMlZ5ZG1WeUxXTmhRREUzTURNNU9ERTVOekF3V1RBVEJnY3Foa2pPClBRSUJCZ2dxaGtqT1BRTUJCd05DQUFRc3k0UXAwSUxBSm4xNmVvUkV0RWZRWlc5cWptMisrR3A3OElBWGdKM1YKeG54ZEVVYVh3dHl5MGd5UGR6eTBKcnVta0ZCVW9DY010dHgvVnVQRlpJU0pvMEl3UURBT0JnTlZIUThCQWY4RQpCQU1DQXFRd0R3WURWUjBUQVFIL0JBVXdBd0VCL3pBZEJnTlZIUTRFRmdRVVhFRytDa0xmeEN5UWdrUDlxeVUwCkFkWFl4K1F3Q2dZSUtvWkl6ajBFQXdJRFJ3QXdSQUlnRmkxT1puYkZNbVh0azl5d01yUDcrMXd6Q2E0UDJ4L3cKS1pLcWQ3dm1BOW9DSUE5akx3N0VEbVZXL2FwOWdlb05XZXIwSGx6U1VNdDRyZlR2ZTRBTGVRYXcKLS0tLS1FTkQgQ0VSVElGSUNBVEUtLS0tLQo=
    server: https://127.0.0.1:6443
  name: default
contexts:
- context:
    cluster: default
    user: default
  name: default
current-context: default
kind: Config
preferences: {}
users:
- name: default
  user:
    client-certificate-data: LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUJrVENDQVRlZ0F3SUJBZ0lJTnVzYks0LzhIMVV3Q2dZSUtvWkl6ajBFQXdJd0l6RWhNQjhHQTFVRUF3d1kKYXpOekxXTnNhV1Z1ZEMxallVQXhOekF6T1RneE9UY3dNQjRYRFRJek1USXpNVEF3TVRrek1Gb1hEVEkwTVRJegpNREF3TVRrek1Gb3dNREVYTUJVR0ExVUVDaE1PYzNsemRHVnRPbTFoYzNSbGNuTXhGVEFUQmdOVkJBTVRESE41CmMzUmxiVHBoWkcxcGJqQlpNQk1HQnlxR1NNNDlBZ0VHQ0NxR1NNNDlBd0VIQTBJQUJPemxqdXZBL0M4Ly9rVEUKMVFlWFR0R3IyRnowTmwzc0x2RHJjd0JHNGRTay85SmVLN1h4ajZJWlJQVUJxemtjWUtGb0laS2Q4NWgvazdCMApRWUJ1ZE0ralNEQkdNQTRHQTFVZER3RUIvd1FFQXdJRm9EQVRCZ05WSFNVRUREQUtCZ2dyQmdFRkJRY0RBakFmCkJnTlZIU01FR0RBV2dCUTdGVDVVaDVMRGg1QTVKNXI4NGFTWFArRUZNVEFLQmdncWhrak9QUVFEQWdOSUFEQkYKQWlFQTNHSnNIYmNsMlhIbDhoUDRwYnVtTE5BY25ycEFVSmJUdFVOc082QjFnazBDSUJPVW1ZbGIyOE5CaGw5RQpwbnJ1MXlHK1NFbkpHa2tVT3MvN25uRlRZWFhHCi0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0KLS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUJlRENDQVIyZ0F3SUJBZ0lCQURBS0JnZ3Foa2pPUFFRREFqQWpNU0V3SHdZRFZRUUREQmhyTTNNdFkyeHAKWlc1MExXTmhRREUzTURNNU9ERTVOekF3SGhjTk1qTXhNak14TURBeE9UTXdXaGNOTXpNeE1qSTRNREF4T1RNdwpXakFqTVNFd0h3WURWUVFEREJock0zTXRZMnhwWlc1MExXTmhRREUzTURNNU9ERTVOekF3V1RBVEJnY3Foa2pPClBRSUJCZ2dxaGtqT1BRTUJCd05DQUFUQ2xaNG9BOW43RmxnU3F0UjBNQ0UrSlFIQmw5dC9LQWUyYVYvWDAxeGsKU0hhNFBrVHFZV3RwWUtHVkVSVHB2Nkh3RElHbzNFVVE4UHFUTDNNZjd4QW5vMEl3UURBT0JnTlZIUThCQWY4RQpCQU1DQXFRd0R3WURWUjBUQVFIL0JBVXdBd0VCL3pBZEJnTlZIUTRFRmdRVU94VStWSWVTdzRlUU9TZWEvT0drCmx6L2hCVEV3Q2dZSUtvWkl6ajBFQXdJRFNRQXdSZ0loQUlERTVacXo0WnFEUExIWjczWmhwUE9uNnVkK05ucWYKVTAra1V6WVdBM2dJQWlFQTJmUEtPVE0zNmdiem9WL1kvMDJ0czk3dHZpOU1GSklWZjFiTElRelBhSU09Ci0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0K
    client-key-data: LS0tLS1CRUdJTiBFQyBQUklWQVRFIEtFWS0tLS0tCk1IY0NBUUVFSUdNMVM3WjhrVUh5YTgwTFNhaGRMaWhka2xBUHVlcUMzdXRINWNEN1NmSkNvQW9HQ0NxR1NNNDkKQXdFSG9VUURRZ0FFN09XTzY4RDhMei8rUk1UVkI1ZE8wYXZZWFBRMlhld3U4T3R6QUViaDFLVC8wbDRydGZHUApvaGxFOVFHck9SeGdvV2doa3Azem1IK1RzSFJCZ0c1MHp3PT0KLS0tLS1FTkQgRUMgUFJJVkFURSBLRVktLS0tLQo=
```
```bash
chmod +x reinstall.sh
```

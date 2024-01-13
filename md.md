```bash
sudo apt update
```
```bash
sudo apt install -y apt-transport-https curl
```
```bash
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key --keyring /usr/share/keyrings/kubernetes-archive-keyring.gpg add -
echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list > /dev/null
```
```bash
sudo apt update
sudo apt install -y kubeadm kubelet kubectl
```
```bash
kubeadm --help
```
```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
```bash
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
```bash
docker --help
```
```bash
wget https://github.com/Mirantis/cri-dockerd/releases/download/v0.3.8/cri-dockerd_0.3.8.3-0.ubuntu-jammy_amd64.deb
```
```bash
sudo dpkg -i cri-dockerd_0.3.8.3-0.ubuntu-jammy_amd64.deb
```
```bash
sudo kubeadm init --cri-socket unix:///var/run/cri-dockerd.sock
```
```bash
kubectl get namespaces
```
```bash
kubectl get pods -n kube-system
```
```bash
kubectl get daemonsets -n kube-system
```

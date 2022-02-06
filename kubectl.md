# kubectl
## binary
Install `kubectl` using:
```bash
VERSION="1.21.0"
mkdir /tmp/kubectl_$VERSION 
cd /tmp/kubectl_$VERSION
curl -LO https://dl.k8s.io/release/v$VERSION/bin/linux/amd64/kubectl
chmod +x kubectl
sudo mv kubectl /usr/bin/kubectl_$VERSION
sudo ln -s /usr/bin/kubectl_$VERSION /usr/bin/kubectl
```

## apt via google repo
see: https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-using-native-package-management
```bash
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg

echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list

sudo apt-get update
sudo apt-get install -y kubectl
```
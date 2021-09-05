# kubectl
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

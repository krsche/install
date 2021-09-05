# helm
Install `helm` using:
```bash
VERSION="3.6.1"
mkdir /tmp/helm_$VERSION
cd /tmp/helm_$VERSION
wget https://get.helm.sh/helm-v$VERSION-linux-amd64.tar.gz
tar -xzf helm-v$VERSION-linux-amd64.tar.gz
chmod +x linux-amd64/helm
sudo mv linux-amd64/helm /usr/bin/helm_$VERSION
sudo ln -s /usr/bin/helm_$VERSION /usr/bin/helm
```

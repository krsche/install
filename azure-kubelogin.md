# Azure Kubelogin
Don't confuse with int128/kubelogin, that is a generic OIDC login client while azure/kubelogin is specific to AKS

```bash
VERSION=v0.0.16
cd `mktemp -d`
wget https://github.com/Azure/kubelogin/releases/download/$VERSION/kubelogin-linux-amd64.zip
unzip kubelogin-linux-amd64.zip
sudo mv bin/linux_amd64/kubelogin /usr/bin/kubelogin_$VERSION
sudo ln -s /usr/bin/kubelogin_$VERSION /usr/bin/kubelogin
```




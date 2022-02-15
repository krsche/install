# Azure Kubelogin
Don't confuse with int128/kubelogin, that is a generic OIDC login client while azure/kubelogin is specific to AKS

```bash
DIR=`mktemp -d` && cd $DIR
wget https://github.com/Azure/kubelogin/releases/download/v0.0.11/kubelogin-linux-amd64.zip
unzip kubelogin-linux-amd64.zip
sudo mv bin/linux_amd64/kubelogin /usr/bin/kubelogin_v0.0.11
sudo ln -s /usr/bin/kubelogin_v0.0.11 /usr/bin/kubelogin
```




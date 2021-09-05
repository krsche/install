# k9s
Install `k9s` using:
```bash
VERSION="0.24.10"
mkdir /tmp/k9s_$VERSION
cd /tmp/k9s_$VERSION
wget https://github.com/derailed/k9s/releases/download/v$VERSION/k9s_v${VERSION}_Linux_x86_64.tar.gz
tar -xzf k9s_v${VERSION}_Linux_x86_64.tar.gz
chmod +x k9s
sudo mv k9s /usr/bin/k9s_$VERSION
sudo ln -s /usr/bin/k9s_$VERSION /usr/bin/k9s
```

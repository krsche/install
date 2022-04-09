# JWT CLI

```bash
VERSION=5.0.2
DIR=`mktemp -d` && cd $DIR
wget https://github.com/mike-engel/jwt-cli/releases/download/$VERSION/jwt-linux.tar.gz
tar -xzf jwt-linux.tar.gz
sudo mv jwt /usr/bin/jwt-5.0.2
sudo ln -s /usr/bin/jwt-5.0.2 /usr/bin/jwt
```

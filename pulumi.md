# Pulumi
```bash
VERSION="3.13.2"
FOLDER=`mktemp -d /tmp/pulumi.XXXXXXXXXX`
cd $FOLDER
wget https://get.pulumi.com/releases/sdk/pulumi-v$VERSION-linux-x64.tar.gz
tar -xzf pulumi-v$VERSION-linux-x64.tar.gz
mv pulumi ~/bin/pulumi_$VERSION
cd ~/bin
for f in pulumi_$VERSION/pulumi*; do ln -fs $f ${f#*/}; done
```
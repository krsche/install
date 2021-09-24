# Node (nodejs)

```bash
VERSION='14.17.6'
cd ~/lib
wget https://nodejs.org/dist/v$VERSION/node-v$VERSION-linux-x64.tar.xz
tar xf node-v$VERSION-linux-x64.tar.xz
rm node-v$VERSION-linux-x64.tar.xz

# add links to ~/bin
cd ~/bin
ln -s ~/lib/node-v$VERSION-linux-x64/bin/node node
ln -s ~/lib/node-v$VERSION-linux-x64/bin/npm npm
ln -s ~/lib/node-v$VERSION-linux-x64/bin/npx npx
```

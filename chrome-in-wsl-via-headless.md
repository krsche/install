# Chrome in WSL for running via --headless

```bash
# Available versions: https://www.ubuntuupdates.org/package/google_chrome/stable/main/base/google-chrome-stable?id=202706
VERSION=95.0.4638.69-1
sudo apt-get install -y curl unzip xvfb libxi6 libgconf-2-4 fonts-liberation
DIR=$(mktemp -d)
cd $DIR
# latest: wget -O chrome.deb  https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
wget -O chrome.deb https://dl.google.com/linux/chrome/deb/pool/main/g/google-chrome-stable/google-chrome-stable_${VERSION}_amd64.deb
sudo dpkg -i chrome.deb
sudo ln -fs /usr/bin/chrome /usr/bin/google-chrome-stable
```
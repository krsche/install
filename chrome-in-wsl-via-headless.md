# Chrome in WSL for running via --headless

```bash
sudo apt-get install -y curl unzip xvfb libxi6 libgconf-2-4 fonts-liberation
DIR=$(mktemp -d)
cd $DIR
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
sudo ln -fs /usr/bin/chrome /usr/bin/google-chrome-stable
```
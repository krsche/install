# STLINK

> **⚠️ Warning**
>
> Not working properly on WSL1 yet...

```bash
sudo apt-get install -y -q gcc build-essential cmake libusb-1.0 libusb-1.0-0-dev libgtk-3-dev git

DEST=~/lib/stlink
mkdir $DEST && cd $DEST && git clone https://github.com/stlink-org/stlink.git . && \
    make clean && \
    make release && \
    make install
```
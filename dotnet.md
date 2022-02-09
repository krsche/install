# .NET (dotnet)

## SDK
### Linux
refs:  
- https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/sdk-6.0.102-linux-x64-binaries
- https://tecadmin.net/how-to-install-net-core-on-ubuntu-20-04/

```bash
# add microsoft ppa
dir=`mktemp -d` && cd $dir
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb
sudo apt update

# install
sudo apt install apt-transport-https
sudo apt install dotnet-sdk-6.0

# test
dotnet
```
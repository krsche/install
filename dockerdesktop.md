# Docker (Desktop for Windows)
see https://github.com/krsche/install/dockerdesktop.md
Download and install from [here](https://docs.docker.com/docker-for-windows/install/)

> ℹ️ Note
> 
> Make sure to *check* `Install required Windows components for WSL2`.  
> This doesn't affect a WSL1 installation!

## Use from WSL1
To use docker from WSL1 some more setup is required:  
- Docker Desktop Settings: 
  - Enable `Expose daemon on tcp://localhost:2375 without TLS`
  - Enable `Use the WSL2 based engine`
  - Disable `Send usage statistics`
- Install docker-ce in WSL (Ubuntu 20.04) and setup:
   ```bash
   # Install pre-requisites
   sudo apt-get install software-properties-common

   # Add docker repo key and verify validity
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   sudo apt-key fingerprint OEBFCD88

   # Add docker repo and update package-list
   sudo add-apt-repository \
      "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
      $(lsb_release -cs) \
      stable"
   sudo apt-get update -y

   # Install docker client
   sudo apt-get install -y docker-ce
   
   # Add current user to docker group
   sudo usermod -aG docker $USER

   # Connect WSL to docker daemon on host (through the daemon exposure enabled above)
   # Only run this if not already in .bashrc (envsetup includes this already)
   # echo "export DOCKER_HOST=tcp://localhost:2375" >> ~/.bashrc && source ~/.bashrc

   # Verify that it works
   docker info
   docker run hello-world
   ```

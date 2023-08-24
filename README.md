# NVIDIA Tao Toolkit Installation

## <u>Prerequisites</u>

#### Tao Package
``` shell
wget --content-disposition https://api.ngc.nvidia.com/v2/resources/nvidia/tao/tao-getting-started/versions/5.0.0/zip -O getting_started_v5.0.0.zip
unzip -u getting_started_v5.0.0.zip  -d ./getting_started_v5.0.0 && rm -rf getting_started_v5.0.0.zip && cd ./getting_started_v5.0.0
```

#### Docker CLI
``` shell
sudo apt update
sudo apt install  ca-certificates  curl  gnupg  lsb-release
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu   $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io -y
```

post installation
```shell
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world
```

### NVIDIA Container Toolkit
```shell
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | apt-key add -
curl -s -L https://nvidia.github.io/nvidia-docker/ubuntu20.04/nvidia-docker.list > /etc/apt/sources.list.d/nvidia-docker.list
apt update
apt -y install nvidia-container-toolkit
systemctl restart docker

```

Go to any 

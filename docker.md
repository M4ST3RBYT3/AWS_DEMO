# Docker y Docker Compose
```cmd
sudo apt update

sudo apt install apt-transport-https curl gnupg-agent ca-certificates software-properties-common -y

# Instalar docker
# Agregar GPGK key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# Descargar el repositorio
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

sudo apt install docker-ce docker-ce-cli containerd.io -y

# Permisos para el usuario
sudo usermod -aG docker $USER && newgrp docker

docker version

# Instalar docker compose
mkdir -p ~/.docker/cli-plugins/  
curl -SL https://github.com/docker/compose/releases/download/v2.3.3/docker-compose-linux-x86_64 -o ~/.docker/cli-plugins/docker-compose

# Asignar los permisos al comando
chmod +x ~/.docker/cli-plugins/docker-compose

docker compose version
```

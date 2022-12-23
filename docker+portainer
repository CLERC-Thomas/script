# Source: https://docs.docker.com/engine/install/debian/
# On supprime de potentielles anciennes installations
apt update
apt upgrade -y
apt remove docker docker-engine docker.io containerd runc

# On installe les paquets nécessaires
apt install -y apt-transport-https ca-certificates curl gnupg lsb-release

# On ajoute la clef GPG officielle de Docker
curl -fsSL https://download.docker.com/linux/debian/gpg | gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# On ajoute le dépôt
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null

# On installe docker engine
apt update
apt install -y docker-ce docker-ce-cli containerd.io 
sudo docker run hello-world

# On installe docker-compose
# Source: https://docs.docker.com/compose/install/
curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose

docker run -d -p 9001:9001 --name=portainer_agent --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/docker/volumes:/var/lib/docker/volumes portainer/agent

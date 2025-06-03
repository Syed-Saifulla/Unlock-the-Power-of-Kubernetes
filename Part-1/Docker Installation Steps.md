# 🐳 Docker Installation and Usage on Ubuntu 22.04

#### Docker can be installed on Linux, macOS, and Windows. Below are the general steps for each platform. For the latest instructions, always refer to the official Docker documentation. 
https://docs.docker.com/engine/install/

## ✅ Step-by-Step: Install Docker Engine on Ubuntu 22.04

### 1. Update the System
```bash
sudo apt update
sudo apt upgrade -y
```

### 2. Install Required Packages
```bash
sudo apt install -y ca-certificates curl gnupg lsb-release
```

### 3. Add Docker’s Official GPG Key
```bash
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

### 4. Set Up the Docker Repository
```bash
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### 5. Install Docker Engine
```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### 6. Verify Docker Installation
```bash
docker --version
```

### 7. Optional: Run Docker as Non-root User
```bash
sudo usermod -aG docker $USER
newgrp docker
```

### 8. Test Docker Installation
```bash
docker run hello-world
```
---

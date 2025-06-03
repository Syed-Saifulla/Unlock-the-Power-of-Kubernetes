# 🐳 Docker Installation and Usage on Ubuntu 22.04

##### Docker can be installed on Linux, macOS, and Windows. Below are the general steps for each platform. For the latest instructions, always refer to the official Docker documentation. 
##### https://docs.docker.com/engine/install/

## ✅ Step-by-Step: Install Docker Engine on Ubuntu 22.04

> ##### ⚠️ **Note**: This guide is intended for use in a **test lab or virtual machine (VM)** environment.
> ##### It is **not recommended for production systems** without proper review.
> ##### The `apt update` and `apt upgrade` commands may change system packages and configurations.


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
![Image](https://github.com/user-attachments/assets/7d63dd93-4ec4-4ecf-8188-df695eb3c75c)


### 6. Verify Docker Installation
```bash
docker --version
```
![Image](https://github.com/user-attachments/assets/6b9d73ad-737b-4823-b384-bdc3271350bd)

### 7. Optional: Run Docker as Non-root User
```bash
sudo usermod -aG docker $USER
newgrp docker
```

### 8. Test Docker Installation
```bash
docker run hello-world
```

![Image](https://github.com/user-attachments/assets/3abbd5c9-4610-4eb9-aa3b-f56ab72ab330)
---

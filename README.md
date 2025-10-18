# Docker Setup Guide

## Prerequisites

### Installing Docker

#### For all Linux distributions
Follow the official Docker installation guide: https://docs.docker.com/engine/install

#### Ubuntu-specific installation

1. Remove any conflicting packages:
```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

2. Set up Docker's official repository:
```bash
# Add Docker's official GPG key
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

3. Install Docker Engine:
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## Setup Instructions

### 1. Download and extract the project files

```bash
git clone https://github.com/Calmantras/artificial-intelligence-jupyter.git
```

### 2. Start the Docker container

> ⚠️ **Note:** Initial startup may take several minutes.

```bash
sudo docker compose up
```

### 3. Add your notebooks

Copy your notebook files from Moodle into the `jupyter` folder.

## Troubleshooting

If you encounter any issues, please open an issue in this repository with detailed information about your environment and the error message.

# Docker Setup on Windows

## Overview

This guide explains how to install and configure Docker Desktop on Windows. It covers the prerequisites, installation steps, verification, and running your first Docker container.

---

## Prerequisites

Before installing Docker, ensure your system meets the following requirements:

* Windows 10 (64-bit) or Windows 11
* Hardware virtualization enabled in BIOS/UEFI
* WSL 2 (Windows Subsystem for Linux) installed
* Administrator privileges

---

## Step 1: Enable Virtualization

1. Restart your computer.
2. Enter BIOS/UEFI settings.
3. Enable:

   * Intel VT-x (Intel CPUs)
   * AMD-V (AMD CPUs)
4. Save the changes and restart Windows.

---

## Step 2: Install WSL 2

Open **PowerShell as Administrator** and run:

```powershell
wsl --install
```

Restart your computer after the installation completes.

Verify WSL installation:

```powershell
wsl --status
```

---

## Step 3: Download Docker Desktop

Download Docker Desktop from the official website:

https://www.docker.com/products/docker-desktop/

Run the installer and keep the default options selected.

During installation, ensure **Use WSL 2 instead of Hyper-V** is enabled if prompted.

Restart your computer if required.

---

## Step 4: Launch Docker Desktop

1. Open Docker Desktop.
2. Accept the license agreement.
3. Wait until Docker Engine starts.
4. Verify that Docker is running successfully.

---

## Step 5: Verify Installation

Open Command Prompt or PowerShell.

Check Docker version:

```bash
docker --version
```

Example output:

```text
Docker version 28.x.x
```

Check Docker information:

```bash
docker info
```

---

## Step 6: Run Your First Container

Run the Hello World container:

```bash
docker run hello-world
```

If Docker is installed correctly, you will see a success message confirming that your installation is working.

---

## Useful Docker Commands

### Check Docker Version

```bash
docker --version
```

### List Running Containers

```bash
docker ps
```

### List All Containers

```bash
docker ps -a
```

### List Docker Images

```bash
docker images
```

### Pull an Image

```bash
docker pull ubuntu
```

### Run Ubuntu Container

```bash
docker run -it ubuntu
```

### Stop a Container

```bash
docker stop <container_id>
```

### Remove a Container

```bash
docker rm <container_id>
```

### Remove an Image

```bash
docker rmi <image_name>
```

---

## Test Docker with Nginx

Pull the Nginx image:

```bash
docker pull nginx
```

Run the container:

```bash
docker run -d -p 8080:80 nginx
```

Open your browser and visit:

```
http://localhost:8080
```

You should see the default Nginx welcome page.

---

## Common Issues

### Docker command not recognized

Restart your terminal or computer after installation.

---

### WSL not installed

Install WSL using:

```powershell
wsl --install
```

---

### Virtualization disabled

Enable Intel VT-x or AMD-V in BIOS/UEFI settings.

---

### Docker Engine not starting

* Restart Docker Desktop.
* Restart WSL:

```powershell
wsl --shutdown
```

Then reopen Docker Desktop.

---

## Project Structure

```
Docker-Setup-Windows/
│
├── README.md
```

---

## Technologies Used

* Docker Desktop
* Windows 10/11
* WSL 2
* PowerShell
* Command Prompt

---

## Learning Outcomes

* Install Docker Desktop on Windows
* Configure WSL 2
* Understand Docker basics
* Pull Docker images
* Run and manage containers
* Verify Docker installation
* Troubleshoot common installation issues

---

## Official Resources

* Docker Documentation: https://docs.docker.com/
* Docker Desktop: https://www.docker.com/products/docker-desktop/
* WSL Documentation: https://learn.microsoft.com/windows/wsl/

---

## License

This project is intended for educational purposes. Feel free to use, modify, and share it for learning and practice.

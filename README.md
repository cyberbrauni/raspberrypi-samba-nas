<!-- Tech Stack & Metadata (Large Style) -->
![Raspberry Pi](https://img.shields.io/badge/Hardware-Raspberry%20Pi%204-C51A4A?style=for-the-badge&logo=Raspberry-Pi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Last Commit](https://img.shields.io/github/last-commit/cyberbrauni/raspberrypi-samba-nas?style=for-the-badge&color=2ea44f)


# raspberrypi-samba-nas
Creating a central hub for saving and sharing files via local network using Docker Container and Samba 

# Raspberry Pi 4 - Dockerized Samba (SMB/CIFS) NAS

A lightweight, containerized Network Attached Storage (NAS) setup on a Raspberry Pi 4 using Docker Compose and Samba. Designed for seamless file sharing across devices on a local area network (LAN).

---

## Key Features
* **Containerized Infrastructure:** Runs completely inside Docker for easy deployment and clean host OS setup.
* **Network Integration:** Easily mapped as a local network drive in Windows File Explorer (`This PC`).
* **High Performance:** Optimized for Raspberry Pi 4 with low memory footprint.
* **Auto-restart:** Configured with `restart: unless-stopped` for reliable recovery after reboot.

---

## Quick Start & Installation

### Prerequisites
* Raspberry Pi 4 running Linux OS
* Docker and Docker Compose installed
* Static IP address assigned to Raspberry Pi (recommended)

### Setup Instructions

1. **Clone the repository:**
   Bash
   git clone [https://github.com/YOUR_USERNAME/raspberrypi-samba-nas.git](https://github.com/YOUR_USERNAME/raspberrypi-samba-nas.git)
   cd raspberrypi-samba-nas

2. **Prepare the storage directory on the host:**
   mkdir -p /home/ema/shared_storage
   sudo chmod -R 777 /home/ema/shared_storage

3. **Deploy the container:**
   docker compose up -d

4. **Connect from Windows:**
   1. Open File Explorer and go to This PC
   2. Right click on This PC and then Add a network location
   3. Specify the folder path:
      \\<RASPBERRY_PI_IP>\SharedStorage
   4. Check Reconnect at sign-in and click Finish

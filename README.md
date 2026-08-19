# raspberrypi-samba-nas
Creating a central hub for saving and sharing files via local network using Docker Container and Samba 

# Raspberry Pi 4 - Dockerized Samba (SMB/CIFS) NAS

A lightweight, containerized Network Attached Storage (NAS) setup on a Raspberry Pi 4 using Docker Compose and Samba. Designed for seamless file sharing across devices on a local area network (LAN).

---

## 🌟 Key Features
* **Containerized Infrastructure:** Runs completely inside Docker for easy deployment and clean host OS setup.
* **Network Integration:** Easily mapped as a local network drive in Windows File Explorer (`This PC`).
* **High Performance:** Optimized for Raspberry Pi 4 with low memory footprint.
* **Auto-restart:** Configured with `restart: unless-stopped` for reliable recovery after reboot.

---

## 📐 Architecture Overview

+-----------------------------------------------------------+
|                      Local Network (LAN)                  |
|                                                           |
|   +------------------+         +----------------------+   |
|   | Windows Client   | <=====> | Raspberry Pi 4       |   |
|   | (Mapped Drive)   |   SMB   |                      |   |
|   +------------------+         |  +----------------+  |   |
|                                |  | Docker Container|  |   |
|                                |  | (dperson/samba) |  |   |
|                                |  +-------+--------+  |   |
|                                |          | Volume    |   |
|                                |  +-------v--------+  |   |
|                                |  | Host Filesystem|  |   |
|                                |  +----------------+  |   |
|                                +----------------------+   |
+-----------------------------------------------------------+

---

## 🚀 Quick Start & Installation

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

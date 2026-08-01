# Self-Hosted Nextcloud Infrastructure with Docker and Cloudflare Zero Trust

## Overview

This project documents the design and deployment of a self-hosted cloud storage platform using Nextcloud, Docker, Ubuntu Server, and Cloudflare Zero Trust Tunnel.

The project was created to provide a private cloud storage solution after reaching the storage limit of a commercial cloud provider. It demonstrates practical experience in server administration, containerisation, storage management, networking, and secure remote access.

---

# Objectives

The objectives of this project were:

- Deploy a private cloud storage platform
- Learn containerised application deployment using Docker
- Configure external storage for increased capacity
- Implement automated mobile photo backups
- Enable secure remote access without exposing the home network
- Develop practical system administration and networking skills

---

# Architecture

```
                         Internet
                            |
                            |
              Cloudflare Zero Trust Tunnel
                            |
                            |
                    Ubuntu Server
                            |
                    Docker Environment
                            |
              ---------------------------
              |                         |
        Nextcloud Container       MariaDB Container
              |
              |
       External NTFS Storage
              |
              |
       Mobile Photo Backups
```

---

# Technologies Used

| Technology | Purpose |
|------------|---------|
| Ubuntu Server | Host operating system |
| Docker | Container deployment and management |
| Nextcloud | Self-hosted cloud storage platform |
| MariaDB | Database service |
| Cloudflare Zero Trust Tunnel | Secure external access |
| NTFS External Drive | Additional storage capacity |

---

# Implementation

## Server Deployment

The server was deployed using Ubuntu Server and configured to run Docker containers.

Docker was used to isolate application services and simplify deployment management.

The deployed containers included:

- Nextcloud application container
- MariaDB database container

---

# Storage Configuration

An external NTFS hard drive was integrated into the server to provide additional storage capacity.

Configuration tasks included:

- Mounting external storage on Ubuntu
- Configuring file permissions
- Ensuring persistent storage availability
- Connecting storage with Nextcloud

Storage architecture:

```
Nextcloud
    |
Docker Volume
    |
Ubuntu Server
    |
External NTFS Drive
```

---

# Automated Photo Backup

The Nextcloud mobile application was configured to automatically upload photos from mobile devices to the self-hosted cloud platform.

This created a personal backup solution after reaching the storage limit of a commercial cloud provider.

Backup workflow:

```
Mobile Device

      |

Nextcloud Mobile Application

      |

Nextcloud Server

      |

External Storage
```

---

# Secure Remote Access

Remote access was implemented using Cloudflare Zero Trust Tunnel.

Instead of exposing the server directly through router port forwarding, the tunnel creates an encrypted connection between the server and Cloudflare's network.

Traditional approach:

```
Internet
   |
Router Port Forwarding
   |
Server
```

Implemented approach:

```
Internet
   |
Cloudflare Network
   |
Encrypted Tunnel
   |
Ubuntu Server
```

Benefits:

- No inbound ports exposed
- Reduced attack surface
- Secure remote connectivity
- Domain-based access control

---

# Docker Deployment

Example running services:

```
CONTAINER          PURPOSE

nextcloud          Cloud storage application

mariadb            Database service
```

Check running containers:

```bash
docker ps
```

View container logs:

```bash
docker logs nextcloud
```

Restart containers:

```bash
docker restart nextcloud
```

---

# Skills Developed

Through this project, I developed practical experience in:

- Linux server administration
- Docker containerisation
- Cloud infrastructure deployment
- Storage management
- File system configuration
- Networking fundamentals
- DNS configuration
- Secure remote access
- Troubleshooting server environments

---

# Security Considerations

Security measures implemented:

- Avoided direct exposure of services using Cloudflare Zero Trust Tunnel
- Used encrypted remote access
- Managed Linux file permissions
- Isolated services using Docker containers
- Maintained separate application and database containers

---

# Future Improvements

Planned improvements:

- Implement server monitoring using Prometheus and Grafana
- Configure automated server backups
- Add intrusion detection and security monitoring
- Improve storage redundancy
- Implement advanced logging
- Add firewall rules and network segmentation

---

# Conclusion

This project provided practical experience in designing, deploying, and maintaining a self-hosted cloud environment.

It combined concepts from:

- Networking
- System administration
- Cloud computing
- Cybersecurity
- Containerisation

The project demonstrates the ability to build and manage real-world infrastructure while solving a practical storage and accessibility problem.

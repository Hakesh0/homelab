# Architecture Overview

This document provides a high-level overview of the architecture used in the
**Secure HomeLab Zero Trust Environment**.

The HomeLab was designed to support secure self-hosting, cybersecurity
experimentation, and private service access without exposing any resources
to the public internet.

---

## Core Design Principles

- **Zero public exposure**: No public IP, no domain, no port forwarding
- **Identity-first access**: All access is authenticated and authorized
- **Defense in depth**: Multiple security layers instead of a single control
- **Ephemeral infrastructure**: Environment can be safely torn down after use
- **Least privilege**: Services and users only have the access they need

---

## Base Platform

- **Operating System**: Ubuntu Server 22.04 LTS  
- **Host Role**: Central node hosting containers and internal services
- **Service Isolation**: Docker containers
- **Service Management**: Coolify (container orchestration)
- **Visibility & Control**: Portainer (host-side container management)

---

## Hosted Services (Private Only)

All services were deployed as Docker containers and remained **inaccessible
from the public internet**.

- **Personal Website** – Deployment and hosting testing
- **Filebrowser** – Secure internal file access
- **Docmost** – Internal documentation and notes
- **Portainer** – Container monitoring and management (host access only)

---

## Remote Access Model

The HomeLab was accessible from anywhere using **secure, encrypted tunnels**
instead of traditional public hosting.

### Access Technologies Used

- **Twingate (Zero Trust Access)**
  - Identity-aware access
  - No open inbound ports
  - Fine-grained access policies

- **Tailscale (Mesh VPN)**
  - Encrypted device-to-device communication
  - Trusted device access
  - Used for simplified administrative connectivity

Both methods ensured:
- End-to-end encryption
- No exposed services
- No reliance on static IP addresses

---

## High-Level Architecture Flow


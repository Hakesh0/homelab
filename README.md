# Secure HomeLab – Zero Trust Architecture

A documentation-driven case study of a **private, security-first HomeLab**
built on **Ubuntu Server 22.04**, designed for **cybersecurity experimentation,
secure self-hosting, and Zero Trust access** — without exposing any services
to the public internet.

> ⚠️ This repository intentionally contains **documentation only**.  
> Live configurations, secrets, IPs, and access details are excluded by design.

---

## 📌 Project Overview

The Secure HomeLab was created to explore **modern secure infrastructure patterns**
using containerization, identity-based access, and encrypted private networking.

The environment was:
- Designed
- Secured
- Validated
- **Intentionally decommissioned**

after achieving its learning objectives, following **attack surface reduction
and lifecycle security best practices**.

---

## 🎯 Objectives

- Build a **private-by-default** self-hosting environment
- Avoid traditional public hosting risks
- Implement **Zero Trust** and **encrypted VPN access**
- Experiment with containerized service deployment
- Practice **secure teardown** after validation
- Document architecture, security decisions, and lessons learned

---

## 🧠 Key Design Principles

- **No public IP**
- **No port forwarding**
- **No public DNS**
- **Identity-first access**
- **Encryption everywhere**
- **Least privilege**
- **Ephemeral infrastructure**

---

## 🏗️ High-Level Architecture

[Image](/network-diagram.png)


All access was performed through **secure, encrypted tunnels**.  
No services were ever exposed directly to the internet.

---

## 🧰 Technology Stack

### Host & Infrastructure
- Ubuntu Server 22.04 LTS
- Docker Engine
- Portainer (container visibility)

### Service Orchestration
- Coolify (self-hosted PaaS)

### Internal Services
- Filebrowser (secure file access)
- Docmost (internal documentation)
- Personal Website (deployment testing)

### Secure Access
- **Twingate** – Identity-based Zero Trust access
- **Tailscale** – Encrypted mesh VPN for trusted devices

---

## 🔒 Security Model

### Zero Trust Access
- Identity-based authentication
- No inbound firewall rules
- Fine-grained service access
- No reliance on static IPs

### VPN Access
- Encrypted device-to-device tunnels
- Secure administrative access
- No exposed endpoints

### Container Isolation
- Each service isolated in its own container
- Reduced blast radius
- Simplified updates and teardown

### Network Exposure
❌ Public IP  
❌ Open ports  
❌ Public DNS  
❌ Internet-facing services  

✔ Private access only  
✔ Encrypted tunnels  
✔ Identity-verified connections  

---

Each section documents **design decisions**, not just tools.

---

## 🔄 Operational Lifecycle

1. Provisioned secure Ubuntu host  
2. Deployed containerized services  
3. Enforced Zero Trust & VPN access  
4. Performed security experimentation  
5. Documented architecture & controls  
6. **Safely decommissioned the lab**

This mirrors real-world security operations where environments are **temporary,
purpose-driven, and responsibly retired**.

---

## 🧠 Why This Lab Was Decommissioned

After achieving its objectives, the HomeLab was intentionally deleted to:

- Reduce residual attack surface
- Avoid maintaining unused infrastructure
- Practice secure lifecycle management
- Reinforce ephemeral infrastructure principles

> Decommissioning unused systems is a **security best practice**, not a failure.

---

## 📘 What This Project Demonstrates

- Practical Zero Trust implementation
- Secure self-hosting without public exposure
- Identity-based access over network trust
- Container security fundamentals
- Threat-aware infrastructure design
- Responsible teardown practices

---

## ⚠️ Disclaimer

This repository **does not include**:
- Live configurations
- Secrets or credentials
- IP addresses or access tokens
- Step-by-step deployment commands

This is intentional and aligns with security best practices.

---

## 👤 Author

**Hakesh M**  
Cybersecurity Enthusiast | SOC & Blue Team Focus  
CTFs • SIEM • Zero Trust • Secure Infrastructure  

---

## 📎 License

This project is provided for **educational and documentation purposes only**.



# Infrastructure Overview

This document describes the core infrastructure used in the
**Secure HomeLab Zero Trust Environment**.

The infrastructure was designed to provide a **secure, flexible, and easily
decommissionable platform** for cybersecurity experimentation, service hosting,
and Zero Trust access validation.

---

## Operating System

### Ubuntu Server 22.04 LTS

- **Base OS**: Ubuntu Server 22.04 LTS
- **Role**: Central host for all services and containers
- **Reason for choice**:
  - Long-term security updates (LTS)
  - Strong community and enterprise adoption
  - Excellent compatibility with container tooling
  - Stable kernel and predictable behavior

The server was used strictly as a **headless system**, accessed only through
secure private tunnels (Twingate / Tailscale).  
No public SSH exposure or public-facing services were configured.

---

## Containerization Layer

### Docker Engine

Docker was used as the primary isolation and deployment mechanism.

#### Why Docker was chosen
- Process isolation between services
- Rapid deployment and teardown
- Reduced configuration drift
- Minimal impact on host OS
- Easy security boundary definition

Each application ran in its own container, preventing direct dependency
or privilege overlap with other services.

---

## Service Orchestration

### Coolify (Self-Hosted PaaS)

Coolify was deployed as a containerized platform to manage application lifecycles.

#### Responsibilities
- Application deployment
- Container lifecycle management
- Environment variable handling
- Internal routing between services

#### Security considerations
- Coolify was **not exposed publicly**
- Access restricted to authenticated users over private tunnels
- No public webhooks or open management ports
- Used strictly for internal orchestration

Coolify allowed rapid experimentation while maintaining a controlled
and private environment.

---

## Container Visibility & Management

### Portainer

Portainer was deployed on the host to provide visibility into
running containers and Docker resources.

#### Usage
- Monitor container health and status
- Inspect container logs
- Perform controlled restarts
- Validate container isolation

#### Security posture
- Access limited to private network only
- No public interface
- Used as an operational visibility tool, not a control plane

---

## Network Exposure Model

- **No public IP address**
- **No port forwarding**
- **No public DNS records**
- **No inbound firewall rules for services**

All network access was handled exclusively through:
- Identity-based Zero Trust (Twingate)
- Encrypted mesh VPN (Tailscale)

This approach significantly reduced the attack surface compared
to traditional self-hosted infrastructure.

---

## Infrastructure Lifecycle

The infrastructure followed an **ephemeral lifecycle model**:

1. Provision host
2. Deploy containers and services
3. Validate security controls
4. Perform experimentation and learning
5. Document architecture and decisions
6. **Intentionally decommission environment**

This mirrors real-world security practices where environments are
built for specific objectives and safely torn down afterward.

---

## Summary

The infrastructure design prioritized:
- Security over convenience
- Private access over public exposure
- Documentation over long-term uptime
- Minimal attack surface

This approach enabled safe self-hosting, realistic security testing,
and clean teardown without residual risk.

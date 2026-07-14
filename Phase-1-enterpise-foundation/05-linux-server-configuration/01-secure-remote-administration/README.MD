# Secure Remote Administration

## Objective

Configure an Ubuntu server for secure remote administration using OpenSSH and verify encrypted connectivity from a dedicated Kali Linux administrative workstation.

---

## Environment

| Component | Configuration |
|-----------|---------------|
| Hypervisor | VMware Workstation Pro 17.6.4 |
| Host OS | Windows 11 |
| Server | Ubuntu 26.04 |
| Client | Kali Linux 2026.2 |
| Protocol | SSH (TCP/22) |

---

## Architecture

```
Kali Linux
     │
     │ SSH (TCP/22)
     ▼
Ubuntu Server
```

---

## Implementation

The following tasks were completed:

- Installed and configured OpenSSH Server on Ubuntu.
- Enabled and started the SSH service.
- Verified the SSH service status.
- Identified the Ubuntu server IP address.
- Verified network connectivity using ICMP (ping).
- Established a secure SSH session from Kali to Ubuntu.
- Executed remote commands to verify successful remote administration.

---

## Validation

- ✅ SSH service running successfully.
- ✅ Ubuntu reachable from Kali.
- ✅ 0% packet loss during connectivity testing.
- ✅ Successful SSH login from Kali.
- ✅ Remote command execution verified.

---

## Challenges & Resolutions

### Incorrect Package Name

**Issue**

Initially attempted to install SSH using an incorrect package name.

**Resolution**

Installed the correct package:

```bash
sudo apt install openssh-server -y
```

---

### SSH Service Inactive

**Issue**

OpenSSH was installed but the SSH service was not running.

**Resolution**

Started the service using `systemctl` and verified it reached the **active (running)** state.

---

### Connection Refused

**Issue**

SSH connection was initially refused because the SSH service had not been started.

**Resolution**

Started the SSH service on Ubuntu and reattempted the connection successfully.

---

### Incorrect IP Address

**Issue**

The first SSH attempt used an incorrect IP address due to a typing mistake.

**Resolution**

Verified the correct IP using `ip a` and established the connection successfully.

---

### VMware Cursor Issue (Known Issue)

The Kali virtual machine occasionally hides the mouse cursor while inside VMware Workstation.

This issue does not impact:

- SSH connectivity
- Networking
- Terminal usage
- Project functionality

The issue has been documented and deferred for future investigation.

---

## Commands Used

```bash
sudo apt install openssh-server -y

sudo systemctl start ssh

sudo systemctl enable ssh

sudo systemctl status ssh

ip a

ping <ubuntu-ip>

ssh secadmin@<ubuntu-ip>

exit
```

---

## Evidence

- 01-ssh-service-running.png
- 02-ping-success.png
- 03-successful-ssh-login.png
- 04-remote-command-execution.png

---

## Enterprise Relevance

SSH is the industry-standard protocol for securely administering Linux servers over untrusted networks. Secure remote administration is a foundational capability used across enterprise infrastructure, cloud environments, DevOps, and Security Operations Centers (SOC).

---

## Skills Demonstrated

- Linux Administration
- OpenSSH Configuration
- Systemd Service Management
- Secure Remote Administration
- ICMP Connectivity Testing
- Network Troubleshooting
- VMware Virtual Networking

---

## Outcome

- ✅ Ubuntu configured as a remotely manageable Linux server.
- ✅ Kali configured as an administrative workstation.
- ✅ Secure SSH communication successfully established.
- ✅ Foundation prepared for SSH hardening in the next phase.

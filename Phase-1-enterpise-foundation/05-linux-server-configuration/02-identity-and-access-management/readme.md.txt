# Identity and Access Management (IAM)

**Status:** In Progress

## Objective

Implement enterprise-style identity and access management by creating dedicated administrative accounts, assigning appropriate privileges, and applying the principle of least privilege.

---

## Scope

This capability will eventually cover:

- User management
- Group management
- Sudo delegation
- Password policies
- File ownership
- File permissions
- Access Control Lists (ACLs)
- Service accounts
- Auditing

This document will be updated as additional IAM capabilities are implemented.

---

## Completed

### Administrative User Creation

Implemented a dedicated administrative account (`secadmin`) instead of relying solely on the installation user.

The account was granted administrative privileges by adding it to the `sudo` group and verified through a successful SSH login from the Kali workstation.

---

## Validation

- ✅ Administrative user created
- ✅ Added to sudo group
- ✅ SSH login successful
- ✅ Administrative privileges verified

---

## Challenges & Resolutions

No significant issues were encountered during this implementation.

---

## Commands Used

```bash
sudo adduser secadmin

sudo usermod -aG sudo secadmin

groups secadmin

sudo whoami
```

---

## Evidence

- 01-secadmin-created.png
- 02-sudo-group-membership.png
- 03-secadmin-ssh-login.png
- 04-sudo-verification.png

---

## Enterprise Relevance

Dedicated administrative accounts improve accountability, support role-based access control (RBAC), and reduce the risks associated with using shared or default administrator accounts.

---

## Skills Demonstrated

- Linux User Management
- Linux Group Management
- Sudo Privilege Delegation
- Identity and Access Management (IAM)
- Secure Remote Administration

---

## Next Steps

- Configure password policies
- Implement additional user groups
- Configure file ownership
- Configure Linux permissions
- Implement Access Control Lists (ACLs)
- Configure sudo policies
- Enable account auditing
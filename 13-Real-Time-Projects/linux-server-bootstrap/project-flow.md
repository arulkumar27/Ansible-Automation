# Project Flow

This project automates the initial configuration of newly provisioned Linux servers.

## Workflow

```text
Provision Linux Server
        │
        ▼
Configure SSH Access
        │
        ▼
Verify Connectivity
        │
        ▼
Run Bootstrap Playbook
        │
        ▼
Gather System Facts
        │
        ▼
Update Operating System
        │
        ▼
Install Required Packages
        │
        ▼
Create Users and Groups
        │
        ▼
Configure SSH Security
        │
        ▼
Configure Timezone
        │
        ▼
Set Hostname
        │
        ▼
Configure MOTD
        │
        ▼
Restart SSH Service
        │
        ▼
Verify Server Health
        │
        ▼
Server Ready for Application Deployment
```

---

## Automation Flow

1. Connect to managed hosts using SSH.
2. Gather Ansible facts.
3. Update the operating system.
4. Install required software packages.
5. Create users and configure privileges.
6. Secure SSH configuration.
7. Configure timezone and hostname.
8. Deploy custom MOTD.
9. Restart affected services using handlers.
10. Verify the server is ready for application deployment.

---

## Expected Outcome

- Consistent server configuration
- Secure SSH configuration
- Standardized software installation
- Automated provisioning
- Reduced manual effort
- Production-ready Linux server

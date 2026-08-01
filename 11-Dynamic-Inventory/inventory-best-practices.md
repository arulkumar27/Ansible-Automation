# Dynamic Inventory Best Practices

## Prefer Dynamic Inventory in Cloud

Use Dynamic Inventory for AWS, Azure, and GCP instead of maintaining static IP addresses.

---

## Use Resource Tags

Organize instances using tags.

Example:

```
Role = webserver

Environment = production

Application = ecommerce
```

This makes grouping hosts easier.

---

## Use IAM Roles

Avoid hardcoding cloud credentials.

Prefer:

- IAM Roles (AWS)
- Managed Identity (Azure)
- Service Accounts (GCP)

---

## Separate Environments

Keep separate inventory configurations for:

- Development
- Testing
- Staging
- Production

---

## Use Private IP Addresses

When Ansible runs inside the same VPC or network, prefer private IP addresses over public IPs.

---

## Validate Inventory

Before running a playbook:

```bash
ansible-inventory --graph
```

Verify the discovered hosts.

---

## Keep Plugins Updated

Install and update required collections.

Example:

```bash
ansible-galaxy collection install amazon.aws
```

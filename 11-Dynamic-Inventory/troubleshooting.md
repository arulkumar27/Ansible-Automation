# Troubleshooting Dynamic Inventory

## No Hosts Found

Possible causes:

- Incorrect region
- Missing instance tags
- Wrong filter
- No running instances

Verify:

```bash
ansible-inventory --graph
```

---

## Authentication Failed

Check:

- AWS CLI configuration
- IAM Role permissions
- Environment variables

Verify:

```bash
aws sts get-caller-identity
```

---

## Plugin Not Found

Install the required collection.

Example:

```bash
ansible-galaxy collection install amazon.aws
```

---

## Host Unreachable

Verify:

- Security Group
- SSH access
- Private/Public IP
- Network ACL
- Route Tables

---

## Empty Inventory

Check:

- Region
- Filters
- Tags
- Running instance state

Run:

```bash
ansible-inventory -i aws-ec2-inventory.yml --list
```

to inspect the generated inventory.

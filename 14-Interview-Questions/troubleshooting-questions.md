# Troubleshooting Interview Questions

## 1. Host shows UNREACHABLE. What will you check?

**Answer:**

I will verify:

- SSH connectivity
- Inventory configuration
- Security Groups / Firewall
- Network ACLs
- Route Tables
- Host availability
- SSH user
- Private key permissions

---

## 2. What does "Permission denied (publickey)" mean?

**Answer:**

It indicates SSH key authentication failed.

Possible reasons:

- Wrong private key
- Wrong user
- Public key missing
- Incorrect file permissions

---

## 3. YAML syntax error occurred. How do you troubleshoot?

**Answer:**

- Validate indentation
- Check spaces instead of tabs
- Verify colons (`:`)
- Run:

```bash
ansible-playbook playbook.yml --syntax-check
```

---

## 4. Handler is not running. Why?

**Answer:**

Possible causes:

- Task didn't report **changed**
- Missing `notify`
- Handler name mismatch
- Playbook failed before handlers executed

---

## 5. Variable is undefined.

**Answer:**

Check:

- Variable spelling
- group_vars
- host_vars
- vars_files
- Variable precedence

---

## 6. Dynamic Inventory returns no hosts.

**Answer:**

Verify:

- AWS Region
- IAM Permissions
- EC2 Tags
- Filters
- Inventory Plugin

---

## 7. Module not found.

**Answer:**

Install the required collection.

```bash
ansible-galaxy collection install amazon.aws
```

---

## 8. Vault password incorrect.

**Answer:**

Verify:

- Vault password
- Password file
- Correct encrypted file

---

## 9. SSH timeout.

**Answer:**

Check:

- Security Group
- Firewall
- SSH Service
- Network Connectivity

---

## 10. Playbook works on one server but not another.

**Answer:**

Compare:

- OS Version
- Installed Packages
- Variables
- Network
- Permissions

# Security Best Practices

## Never Store Secrets in Plain Text

Use:

- Ansible Vault
- Environment Variables
- Secret Management Services

---

## Disable Root Login

Configure SSH securely.

```
PermitRootLogin no
```

---

## Use SSH Keys

Prefer SSH key authentication over passwords.

---

## Protect Sensitive Files

Example:

```yaml
mode: "0600"
```

---

## Use Least Privilege

Only use `become: true` when required.

---

## Validate Configurations

Example:

```bash
nginx -t
```

before restarting services.

---

## Secure Version Control

Never commit:

- passwords
- API keys
- private keys
- vault password files

to Git repositories.

---

## Keep Systems Updated

Regularly apply security updates and patches.

# Ansible Vault Best Practices

## Encrypt Sensitive Data

Store sensitive information inside Vault.

Examples:

- Passwords
- API Keys
- Tokens
- Certificates
- Cloud Credentials

---

## Never Store Plain Text Secrets

Avoid:

```yaml
database_password: Password123
```

Instead:

```
ansible-vault encrypt secrets.yml
```

---

## Keep Password Files Secure

Protect:

```
vault.pass
```

with:

```bash
chmod 600 vault.pass
```

Never upload it to GitHub.

---

## Encrypt Only Sensitive Information

Do not encrypt everything.

Encrypt only:

- Credentials
- Keys
- Tokens
- Certificates

---

## Separate Vault Files

Examples:

```
development.yml

staging.yml

production.yml
```

This simplifies environment management.

---

## Use vars_files

Load encrypted variables using:

```yaml
vars_files:
  - secrets.yml
```

---

## Rotate Secrets

Update passwords and API keys periodically.

Re-encrypt Vault files after changes.

---

## Use Different Passwords

Use different Vault passwords for:

- Development
- Testing
- Production

to improve security.

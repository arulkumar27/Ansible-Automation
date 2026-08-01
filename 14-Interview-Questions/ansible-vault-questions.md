# Ansible Vault Interview Questions

## 1. What is Ansible Vault?

A built-in Ansible feature used to encrypt sensitive information.

---

## 2. Why do we use Vault?

To securely store:

- Passwords
- API Keys
- Tokens
- Cloud Credentials

---

## 3. Create a Vault.

```bash
ansible-vault create secrets.yml
```

---

## 4. Encrypt a file.

```bash
ansible-vault encrypt secrets.yml
```

---

## 5. Decrypt a file.

```bash
ansible-vault decrypt secrets.yml
```

---

## 6. Edit an encrypted file.

```bash
ansible-vault edit secrets.yml
```

---

## 7. View encrypted content.

```bash
ansible-vault view secrets.yml
```

---

## 8. Execute playbook with Vault.

```bash
ansible-playbook site.yml --ask-vault-pass
```

---

## 9. Use a Vault password file.

```bash
ansible-playbook site.yml \
--vault-password-file vault.pass
```

---

## 10. Best Practice?

Never store:

- vault.pass
- passwords
- API keys

inside GitHub repositories.

# Vault Password File

Instead of entering the Vault password every time, Ansible can read it from a password file.

## Create a Password File

```bash
echo "MyVaultPassword" > vault.pass
```

Restrict file permissions.

```bash
chmod 600 vault.pass
```

---

## Run a Playbook

```bash
ansible-playbook site.yml \
--vault-password-file vault.pass
```

---

## Encrypt Using Password File

```bash
ansible-vault encrypt secrets.yml \
--vault-password-file vault.pass
```

---

## View Vault

```bash
ansible-vault view secrets.yml \
--vault-password-file vault.pass
```

---

## Best Practice

Do not commit:

```
vault.pass
```

to GitHub.

Add it to:

```
.gitignore
```

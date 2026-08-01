# Decrypt a Vault File

Decrypt a file permanently.

```bash
ansible-vault decrypt secrets.yml
```

After decryption:

```yaml
mysql_password: Password123

api_token: abcdef123456
```

Decrypt multiple files:

```bash
ansible-vault decrypt db.yml api.yml credentials.yml
```

Re-encrypt the file:

```bash
ansible-vault encrypt secrets.yml
```

> Only decrypt files when necessary. Production repositories should keep secrets encrypted.

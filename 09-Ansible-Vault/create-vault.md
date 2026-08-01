# Create an Ansible Vault

Create a new encrypted file.

```bash
ansible-vault create secrets.yml
```

An editor opens automatically.

Example:

```yaml
database_password: MySecurePassword

api_key: XXXXXXXXXXXXX

aws_access_key: XXXXXXXXX

aws_secret_key: XXXXXXXXX
```

Save and exit.

The file is now encrypted.

---

## Verify File

```bash
cat secrets.yml
```

Output:

```
$ANSIBLE_VAULT;1.1;AES256
623861643732...
```

The contents are unreadable because they are encrypted.

# Encrypt an Existing File

Suppose you already have a file.

Example:

```yaml
mysql_password: Password123

api_token: abcdef123456
```

Encrypt the file.

```bash
ansible-vault encrypt secrets.yml
```

After encryption:

```
$ANSIBLE_VAULT;1.1;AES256
6438396438...
```

Run multiple files:

```bash
ansible-vault encrypt db.yml api.yml credentials.yml
```

Verify encryption:

```bash
cat secrets.yml
```

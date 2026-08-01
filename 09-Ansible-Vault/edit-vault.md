# Edit an Encrypted Vault

You do not need to decrypt a Vault file before making changes.

Edit the encrypted file directly:

```bash
ansible-vault edit secrets.yml
```

Enter the Vault password.

The editor opens with the decrypted content.

Example:

```yaml
database_password: NewPassword123

api_key: new-api-key

aws_secret_key: updated-secret
```

Save and exit.

Ansible automatically encrypts the file again before saving it.

This is the recommended method for updating encrypted files.

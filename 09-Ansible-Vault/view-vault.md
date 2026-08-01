# View an Encrypted Vault

View the contents of an encrypted Vault file without decrypting it permanently.

## View a Vault File

```bash
ansible-vault view secrets.yml
```

Enter the Vault password.

Example output:

```yaml
database_password: MySecurePassword

api_key: xxxxxxxxxxxxx

aws_access_key: AKIAxxxxxxxxxxxx

aws_secret_key: xxxxxxxxxxxxxxxxxxxxx
```

The file remains encrypted after viewing.

---

## View Multiple Vault Files

```bash
ansible-vault view database.yml
```

```bash
ansible-vault view credentials.yml
```

Viewing a Vault file is safer than decrypting it when you only need to inspect its contents.

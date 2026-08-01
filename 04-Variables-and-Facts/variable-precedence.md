# Variable Precedence

When the same variable is defined in multiple places, Ansible follows a precedence order.

Highest Priority

1. Extra Variables (`-e`)
2. Task Variables
3. Block Variables
4. Role Variables
5. Play Variables
6. Host Variables
7. Group Variables
8. Inventory Variables
9. Role Defaults

## Example

Inventory

```yaml
package_name: nginx
```

Playbook

```yaml
package_name: apache2
```

Command Line

```bash
ansible-playbook site.yml -e "package_name=docker.io"
```

Final Value

```
docker.io
```

Extra variables always have the highest precedence.

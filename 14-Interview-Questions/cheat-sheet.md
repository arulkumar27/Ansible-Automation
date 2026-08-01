# Ansible Cheat Sheet

## Ad-Hoc Commands

```bash
ansible all -m ping
```

```bash
ansible all -m setup
```

```bash
ansible all -a "df -h"
```

---

## Playbook

```bash
ansible-playbook site.yml
```

```bash
ansible-playbook site.yml --check
```

```bash
ansible-playbook site.yml --syntax-check
```

---

## Inventory

```bash
ansible-inventory --list
```

```bash
ansible-inventory --graph
```

---

## Vault

```bash
ansible-vault create secrets.yml
```

```bash
ansible-vault encrypt secrets.yml
```

```bash
ansible-vault decrypt secrets.yml
```

```bash
ansible-vault edit secrets.yml
```

---

## Galaxy

```bash
ansible-galaxy install geerlingguy.nginx
```

```bash
ansible-galaxy collection install amazon.aws
```

---

## Frequently Used Modules

- package
- apt
- dnf
- service
- user
- group
- file
- copy
- template
- command
- shell
- uri
- cron
- hostname

---

## Important Keywords

- hosts
- tasks
- handlers
- notify
- vars
- register
- when
- loop
- become
- delegate_to
- run_once
- serial
- tags

# Naming Conventions

Use meaningful and consistent names.

## Playbooks

Good:

```
install-nginx.yml
```

Bad:

```
test.yml
```

---

## Variables

Good:

```yaml
application_name

database_user

nginx_port
```

Bad:

```yaml
a

b

temp
```

---

## Roles

Good:

```
common

nginx

docker

mysql
```

---

## Tasks

Always provide descriptive names.

Good:

```yaml
- name: Install Nginx
```

Bad:

```yaml
- name: Task 1
```

Descriptive task names make playbook output easier to understand.

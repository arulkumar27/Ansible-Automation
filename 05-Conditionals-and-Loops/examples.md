# Real-Time Examples

## Example 1 – Install Package Only on Ubuntu

```yaml
when: ansible_distribution == "Ubuntu"
```

---

## Example 2 – Install Docker on Multiple Servers

```yaml
loop:
  - docker.io
  - docker-compose
```

---

## Example 3 – Retry Until Application Starts

```yaml
retries: 10
delay: 5
until: app_status is succeeded
```

---

## Example 4 – Ignore Read-Only Changes

```yaml
changed_when: false
```

---

## Example 5 – Fail Deployment if Disk is Full

```yaml
failed_when: "'100%' in disk_usage.stdout"
```

---

## Example 6 – Create Multiple Users

```yaml
loop:
  - devops
  - developer
  - admin
```

---

## Example 7 – Install Package Based on Operating System

```yaml
when: ansible_os_family == "Debian"
```

---

## Example 8 – Restart Service Only When Configuration Changes

```yaml
notify: Restart Nginx
```

---

## Example 9 – Process Multiple Configuration Files

```yaml
loop:
  - nginx.conf
  - app.conf
  - database.conf
```

---

## Example 10 – Choose Environment Dynamically

```yaml
{{ "Production" if inventory_hostname == "web1" else "Development" }}
```

# Error Handling Best Practices

## Use `block`, `rescue`, and `always`

Group related tasks together and define recovery steps.

---

## Don't Ignore Every Error

Use:

```yaml
ignore_errors: true
```

only for non-critical tasks.

---

## Use `failed_when`

Define custom failure conditions when module defaults are not sufficient.

Example:

```yaml
failed_when: "'FAILED' in command_output.stdout"
```

---

## Use `changed_when`

Prevent read-only commands from appearing as changed.

Example:

```yaml
changed_when: false
```

---

## Stop Critical Deployments

Use:

```yaml
any_errors_fatal: true
```

when failures on one host should stop execution everywhere.

---

## Log Important Failures

Record failures for troubleshooting and auditing.

---

## Validate Before Restarting Services

Example:

```bash
nginx -t
```

Restart only after validation succeeds.

---

## Design Idempotent Playbooks

Playbooks should be safe to run multiple times without introducing unnecessary changes or failures.

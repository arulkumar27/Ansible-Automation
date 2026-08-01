# Advanced Interview Questions

## 1. What is a Strategy Plugin?

A Strategy Plugin controls how tasks are executed across multiple hosts.

Examples:

- linear
- free
- debug

---

## 2. What is the purpose of Forks?

Forks determine how many hosts Ansible can manage in parallel.

---

## 3. What is Async in Ansible?

Async allows long-running tasks to execute without blocking the playbook.

---

## 4. What is a Rolling Update?

A rolling update upgrades a subset of servers at a time to minimize downtime.

---

## 5. What is `serial`?

`serial` controls how many hosts are processed simultaneously during a play.

---

## 6. What is Check Mode?

Check Mode simulates playbook execution without making changes.

---

## 7. What is Diff Mode?

Diff Mode displays differences before and after changes to files managed by Ansible.

---

## 8. What are Collections?

Collections are packages containing roles, modules, plugins, and documentation that extend Ansible functionality.

---

## 9. How do you optimize Ansible performance?

- Increase forks
- Disable fact gathering when unnecessary
- Use handlers
- Use dynamic inventory
- Prefer built-in modules

---

## 10. What are Callback Plugins?

Callback Plugins customize Ansible output, logging, and notifications.

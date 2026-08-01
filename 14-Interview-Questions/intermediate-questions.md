# Intermediate Interview Questions

## 1. Difference between Playbook and Role

A Playbook defines automation tasks, while a Role organizes those tasks into a reusable and modular structure.

---

## 2. Difference between group_vars and host_vars

- `group_vars` stores variables shared by all hosts in a group.
- `host_vars` stores variables specific to an individual host.

---

## 3. Difference between Static and Dynamic Inventory

Static Inventory contains manually maintained host entries, whereas Dynamic Inventory automatically discovers hosts from cloud providers such as AWS, Azure, or GCP.

---

## 4. What is the `register` keyword?

`register` stores the output of a task in a variable so it can be used by later tasks.

---

## 5. What is the `when` statement?

`when` executes a task only if a specified condition evaluates to true.

---

## 6. Why do we use loops?

Loops execute the same task repeatedly for multiple items, reducing duplicate code.

---

## 7. What are Handlers?

Handlers are special tasks triggered by `notify` that execute only when a task reports a change.

---

## 8. What is a Jinja2 Template?

A Jinja2 template generates dynamic configuration files using variables, conditions, and loops.

---

## 9. Difference between `include_tasks` and `import_tasks`

- `include_tasks` is processed dynamically at runtime.
- `import_tasks` is processed statically before execution.

---

## 10. What is `delegate_to`?

`delegate_to` executes a task on a different host instead of the current managed host.

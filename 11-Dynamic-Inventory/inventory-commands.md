# Dynamic Inventory Commands

## List All Hosts

```bash
ansible-inventory -i aws-ec2-inventory.yml --list
```

---

## Display Inventory Graph

```bash
ansible-inventory -i aws-ec2-inventory.yml --graph
```

---

## List Specific Host

```bash
ansible-inventory \
-i aws-ec2-inventory.yml \
--host web-server-01
```

---

## Test Inventory

```bash
ansible all \
-i aws-ec2-inventory.yml \
-m ping
```

---

## Execute Playbook

```bash
ansible-playbook \
-i aws-ec2-inventory.yml \
site.yml
```

---

## View Parsed Inventory

```bash
ansible-inventory \
-i aws-ec2-inventory.yml \
--yaml
```

---

## Verify Inventory Plugin

```bash
ansible-doc -t inventory amazon.aws.aws_ec2
```

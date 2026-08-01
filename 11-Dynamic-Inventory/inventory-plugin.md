# Inventory Plugins

Inventory plugins allow Ansible to retrieve host information dynamically from external sources.

## Common Inventory Plugins

### AWS

```
amazon.aws.aws_ec2
```

### Azure

```
azure.azcollection.azure_rm
```

### Google Cloud

```
google.cloud.gcp_compute
```

### VMware

```
community.vmware.vmware_vm_inventory
```

### OpenStack

```
openstack.cloud.openstack
```

---

## Install Collections

AWS

```bash
ansible-galaxy collection install amazon.aws
```

Azure

```bash
ansible-galaxy collection install azure.azcollection
```

Google Cloud

```bash
ansible-galaxy collection install google.cloud
```

---

## View Plugin Documentation

```bash
ansible-doc -t inventory amazon.aws.aws_ec2
```

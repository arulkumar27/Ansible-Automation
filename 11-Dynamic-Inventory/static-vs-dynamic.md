# Static Inventory vs Dynamic Inventory

## Static Inventory

A manually maintained inventory file containing hostnames or IP addresses.

Example:

```ini
[webservers]

web1 ansible_host=192.168.1.10

web2 ansible_host=192.168.1.11
```

### Advantages

- Simple
- Easy to configure
- Suitable for small environments

### Disadvantages

- Manual updates
- Difficult to maintain
- Not suitable for cloud environments

---

## Dynamic Inventory

Hosts are automatically discovered from cloud providers.

Example:

- AWS EC2
- Azure Virtual Machines
- Google Compute Engine

### Advantages

- Automatically discovers new servers
- Removes terminated servers
- No manual inventory maintenance
- Ideal for cloud environments

### Disadvantages

- Requires cloud credentials
- More initial configuration

---

## When to Use

Static Inventory

- Small labs
- Learning
- Fixed infrastructure

Dynamic Inventory

- Production
- Cloud Infrastructure
- Auto Scaling
- Kubernetes Worker Nodes

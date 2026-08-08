# Multi-Server Configuration with Ansible Roles

This project demonstrates how Ansible Roles can be used to automate configuration across multiple Linux servers.

## Architecture

* 1 Ansible Controller
* 2 Web Servers
* 1 Application Server

## Roles Used

* `common` – Basic Linux packages and user configuration
* `nginx` – Nginx installation and web page deployment
* `docker` – Docker installation and service configuration
* `app` – Flask application deployment with systemd
* `monitoring` – Basic server monitoring using sysstat and htop

## Technologies

* Ansible
* Ubuntu Linux
* Nginx
* Docker
* Python Flask
* systemd
* Jinja2

## Run

Test connectivity:

```bash
ansible all -m ping
```

Check syntax:

```bash
ansible-playbook site.yml --syntax-check
```

Run the automation:

```bash
ansible-playbook site.yml
```

## Result

Ansible automatically configures the web and application servers using reusable roles and maintains the required server state.

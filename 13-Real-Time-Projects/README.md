# Real-Time Ansible Projects

This directory contains real-world infrastructure automation projects built using Ansible. Each project demonstrates how Ansible can be used to automate common system administration, configuration management, application deployment, and cloud operations.

These projects are based on practical DevOps workflows and reflect tasks commonly performed by Cloud Engineers, DevOps Engineers, Linux Administrators, and Site Reliability Engineers (SREs).

---

# Objectives

The primary objectives of these projects are to:

* Automate repetitive infrastructure tasks
* Configure Linux servers consistently
* Reduce manual intervention
* Improve deployment speed
* Maintain infrastructure using Infrastructure as Code (IaC)
* Follow production-ready automation practices
* Demonstrate real-world Ansible use cases

---

# Projects Included

## 1. Linux Server Bootstrap

Automates the initial configuration of newly provisioned Linux servers.

Typical tasks include:

* Updating packages
* Creating users
* Configuring SSH
* Setting timezone
* Installing common utilities
* Configuring sudo access

---

## 2. Web Server Deployment

Automates complete web server provisioning.

Features include:

* Installing Nginx or Apache
* Deploying website files
* Configuring virtual hosts
* Managing services
* Performing configuration validation

---

## 3. Docker Host Setup

Automates Docker installation and configuration.

Tasks include:

* Installing Docker Engine
* Enabling Docker service
* Configuring Docker daemon
* Adding users to Docker group
* Verifying Docker installation

---

## 4. LAMP Stack Deployment

Deploys a complete LAMP stack.

Components:

* Linux
* Apache
* MySQL
* PHP

Suitable for hosting PHP-based web applications.

---

## 5. MySQL Server Setup

Automates MySQL server deployment and configuration.

Tasks include:

* Installing MySQL
* Starting services
* Creating databases
* Creating users
* Granting privileges
* Configuring secure settings

---

## 6. User Management Automation

Automates Linux user administration.

Examples include:

* Creating users
* Creating groups
* Configuring SSH keys
* Managing sudo access
* Removing inactive users

---

## 7. Application Deployment

Automates application deployment across multiple servers.

Typical workflow:

* Create deployment directories
* Copy application artifacts
* Deploy configuration files
* Restart application services
* Verify application health

---

## 8. Server Hardening

Applies security best practices to Linux servers.

Examples include:

* Disable root login
* Disable password authentication
* Configure firewall
* Apply secure file permissions
* Enable automatic security updates

---

## 9. AWS EC2 Configuration

Automates configuration of Amazon EC2 instances.

Tasks include:

* Dynamic inventory
* Package installation
* Web server deployment
* Docker installation
* Security configuration
* Health verification

---

# Skills Demonstrated

These projects demonstrate practical experience with:

* Configuration Management
* Infrastructure Automation
* Linux Administration
* Server Provisioning
* Package Management
* Service Management
* User Management
* Jinja2 Templates
* Handlers
* Roles
* Dynamic Inventory
* Ansible Vault
* Error Handling
* AWS EC2 Automation
* Production Deployment

---

# Technologies Used

* Ansible
* Linux
* Ubuntu
* RHEL / CentOS
* Nginx
* Apache HTTP Server
* Docker
* MySQL
* OpenSSH
* AWS EC2
* YAML
* Jinja2

---

# Project Workflow

```text
Developer
    │
    ▼
Git Repository
    │
    ▼
Ansible Control Node
    │
    ├───────────────┐
    │               │
    ▼               ▼
Web Servers     Database Servers
    │               │
    ▼               ▼
Application     MySQL
Deployment      Configuration
```

---

# Best Practices Followed

* Idempotent playbooks
* Modular automation
* Built-in Ansible modules
* Reusable variables
* Dynamic configuration using Jinja2
* Secure secret management with Ansible Vault
* Event-driven handlers
* Production-ready project organization
* Validation before service restart
* Consistent naming conventions

---

# Learning Outcomes

After completing these projects, you will understand how to:

* Automate Linux server administration
* Deploy production-ready web servers
* Configure Docker hosts
* Provision application infrastructure
* Manage users securely
* Configure databases automatically
* Secure Linux servers
* Automate AWS EC2 environments
* Build reusable Ansible automation for real-world infrastructure

---

# Target Audience

These projects are suitable for:

* DevOps Engineers
* Cloud Engineers
* Linux System Administrators
* Site Reliability Engineers (SRE)
* Infrastructure Engineers
* Students learning Ansible
* Professionals preparing for technical interviews

---

# Repository Goal

The purpose of this directory is to demonstrate practical Ansible automation skills through realistic infrastructure scenarios rather than simple examples. Each project reflects common operational tasks performed in production environments and follows modern automation practices.

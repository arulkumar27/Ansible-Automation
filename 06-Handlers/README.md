# Ansible Handlers

Handlers are special tasks that run **only when notified** by another task. They are primarily used to restart, reload, or refresh services after configuration changes, ensuring idempotent and efficient automation.

Unlike normal tasks, handlers execute **once at the end of a play**, even if multiple tasks notify the same handler.

## Topics Covered

- Basic Handlers
- Multiple Handlers
- Notify
- Listen
- Handler Execution Flow
- Handler Best Practices
- Real-Time Examples

## Common Use Cases

- Restart Nginx after updating configuration
- Restart Apache after deploying a website
- Reload Systemd after adding a service
- Restart Docker after changing daemon configuration
- Restart MySQL after updating configuration

## Skills Demonstrated

- Event-Driven Automation
- Idempotent Configuration
- Service Management
- Production Best Practices

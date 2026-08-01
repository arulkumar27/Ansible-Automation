# Scenario-Based Interview Questions

## Scenario 1

Your Nginx deployment failed because of an invalid configuration file.

**Answer:**

I would validate the configuration using `nginx -t`, identify the syntax error, restore the previous configuration if necessary, and restart the service only after successful validation.

---

## Scenario 2

One server is unreachable during playbook execution.

**Answer:**

I would verify network connectivity, SSH access, inventory configuration, security group or firewall rules, and ensure the remote host is powered on and reachable.

---

## Scenario 3

You need to deploy an application with zero downtime.

**Answer:**

I would perform a rolling deployment using `serial`, validate each server after deployment, and use a load balancer to remove and re-add instances during the update.

---

## Scenario 4

A package installation fails on one host.

**Answer:**

I would review the package manager logs, verify repository availability, check network connectivity, and use `block` and `rescue` to handle the failure gracefully.

---

## Scenario 5

A deployment changed a configuration but the service was not restarted.

**Answer:**

I would verify that the task includes a `notify` statement and confirm the corresponding handler is correctly defined and triggered.

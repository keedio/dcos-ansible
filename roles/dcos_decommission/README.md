# Decommission DC/OS node

This role can be used to decommission a node from DC/OS cluster. To use this role, just put a node to be decommissed in the [decommission_node] group of inventory. The following tasks are performed:

  * Check if node runs in the cluster
  * Put a node in a maintenance window  
  * Draining node and shutdown

# Requirements

* DC/OS cluster >=1.11
* The node must be running in the cluster

# Example playbook

```
---
- name: Decommission Node
  hosts: decommission_node
  connection: local
  become: false
  
  tasks:
    - include_role:
        name: dcos_decommission
```
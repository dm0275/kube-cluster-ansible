Kubernetes Ansible Role
=========

This Ansible role can be used to provision a Kubernetes cluster with both a master and worker nodes.

Requirements
------------

The role has only been tested on Ubuntu

Role Variables
--------------
|Variable Name        | Description           | Default Value           |
| ------------------- | ----------------------| ----------------------- |
|`user`               | Default login user    | `ubuntu`                |
|`docker_version`     | Docker engine version | `18.06.1~ce~3-0~ubuntu` |
|`kubernetes_version` | Kubernetes version    | `1.14.7-00`             |


Example Playbook
----------------

```yaml
- hosts: master-server
  roles:
    - role: common
    - role: master

- hosts: worker-servers
  roles:
    - role: common
    - role: worker
```

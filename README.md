Kubernetes Ansible Role
=========

This Ansible role can be used to provision a Kubernetes cluster with both a master and worker nodes. This is made up by three roles that are used to configure the master server and worker servers, the roles are:
|Role Name        | Description           |
| ----------------| ----------------------|
|`common`         | This role needs to be applied to both the master and worker servers |
|`master`         | This role should only be applied to the master server |
|`worker`         | This role should only be applied to worker nodes |

Requirements
------------

The `master` and `worker` roles depend on the `common` role.

Role Variables
--------------
|Variable Name        | Description           | Default Value           |
| ------------------- | ----------------------| ----------------------- |
|`user`               | Default login user    | `ubuntu`                |
|`docker_version`     | Docker engine version | `18.06.1~ce~3-0~ubuntu` |
|`kubernetes_version` | Kubernetes version    | `1.14.7-00`             |

Additional variables can be found in each role.

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

Redpanda Ansible Role
=========

This Ansible role is derived from Vectorized.io's [playbooks](https://github.com/vectorizedio/deployment-automation/tree/main/ansible/playbooks).

This role will:

* derive a unique `node_uuid` based on EC2 instance tags and AZ placement
* install Redpanda dependencies
* prepare local instance store disks
* install Redpanada
* template out a configuration file

It makes the following assumptions:

* cluster instances include metadata in EC2 tags (presumably launched through Terraform)
* instances include local NVMe instance store(s)

An example `redpanda.yml` file is included that pulls EC2 tags into named facts.

Platforms
---------

* Ubuntu (tested on `focal`)

Role Variables
--------------
The following variables are available for override.

```
ec2_tag_cluster               # name of the Redpanda cluster
ec2_tag_env.                  # name of envionrment (prod/non-prod)
ec2_tag_role                  # cluster role
ec2_tag_index	                 # node ID
ghostname                     # derived hostname
```


Dependencies
------------

None

License
-------

Apache 2.0

Author Information
------------------
Use github issues for bugs in this repo.

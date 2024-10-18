# Infrastructure definition for KUDE platform using ansible

This repository contains the infrastructure definition for the KUDE platform using ansible. It is a collection of ansible playbooks that can be used to deploy the KUDE platform on a set of machines.

## Prerequisites

Ansible must be installed on the machine where you want to run the playbooks. 

## Install platform

To install the platform, you need to run the following command:

```bash 
ansible-playbook install-platform.yaml -i inventory.yaml
```

This playbook includes:
- Installing docker on all the machines
- Installing kubernetes
- Installing kueue and configuring it


## Install monitoring components

To install the monitoring components, you need to run the following command:

```bash 
ansible-playbook install-monitoring.yaml -i inventory.yaml
```

This playbook includes:
- Installing prometheus

## Build and update dockerfiles
To build and update the dockerfiles, you need to run the following command:

```bash 
ansible-playbook build-dockerfiles.yaml -i inventory.yaml
```

This playbook includes:
- Clone and build all available dockerfiles and push them to the docker registries on the machines

## Uninstall kueue

To uninstall the kueue components, you need to run the following command:

```bash 
ansible-playbook uninstall-kueue.yaml -i inventory.yaml
```

This playbook includes:
- Removing the kueue components


# Other how-to guides

## Add ssh key to machines
```bash
ssh-copy-id -i ~/.ssh/id_rsa.pub pi@pi-master.local
```
# Ansible Deployment for WiMoVE

This repository contains the ansible playbooks we use for deployment. We use `Ubuntu 22.10` hosts as gateway and route reflector. The gateway requires `netplan > 105.0` to create vxlan interfaces with netplan. You need ansible on your host to use the playbooks. You can find documentation on how to do this [here](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html). Then install the `openwrt-role` via

```bash
ansible-galaxy install -r requirements.yml
```

To use the playbooks, create an `inventory.yml` from the `example-inventory.yml`. If you have any questions, feel free to open an issue.
After creating an inventory apply the configuration using the following command:

```bash
ansible-playbook -i inventory.yml install.yml -K
```

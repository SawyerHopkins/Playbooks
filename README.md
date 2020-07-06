# DEVELOPER PLAYBOOKS

Start by creating a new development virtual machine ([Debian 10](https://debian.org/distrib/netinst)), and installing [ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-debian). The development environment can then be provisioned playing the `site.yml` file, or by manually executing playbooks starting with `init.playbook.yml`.

```sh
su
ansible-playbook --connection=local --inventory local.inventory, site.yml
// OR
ansible-playbook --connection=local --inventory local.inventory, init.playbook.yml [PLAYBOOK_NAME].playbook.yml ...
```

Once the provisioning is complete, create an SSH key for the development (non-root) user. Register this with the appropriate development services e.g. [git](https://github.com/settings/keys).

```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

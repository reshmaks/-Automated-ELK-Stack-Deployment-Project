## Downloading and Configuring the Container

In this step, you had to:
- Add your new VM to the Ansible `hosts` file.
- Create a new Ansible playbook to use for your new ELK virtual machine.
- The header of the Ansible playbook can specify a different group of machines as well as a different remote user (in case you did not use the same admin name):

```bash
- name: Config elk VM with Docker
hosts: elk
remote_user: sysadmin
become: true
tasks:
```

- Before you can run the elk container, we need to increase the memory:

```yaml
- name: Use more memory
sysctl:
name: vm.max_map_count
value: '262144'
state: present
reload: yes
```
- This is a system requirement for the ELK container. More info [at the `elk-docker` documentation](https://elk-docker.readthedocs.io/#prerequisites).
- The playbook should then install the following services:
- `docker.io`
- `python3-pip`
- `docker`, which is the Docker Python pip module.


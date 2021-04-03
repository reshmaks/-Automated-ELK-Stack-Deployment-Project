## 2. Creating a New VM

Set up a new virtual machine to run ELK.

- SSH into your Jump-Box using `ssh username@jump.box.ip`

- Check for your Ansible container:

```bash
RedAdmin@Jump-Box-Provisioner:~$ sudo docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```

- Locate the container name:

```bash
RedAdmin@Jump-Box-Provisioner:~$ sudo docker container list -a
CONTAINER ID        IMAGE                    COMMAND             CREATED             STATUS                    PORTS               NAMES
b911d440b690        cyberxsecurity/ansible   "/bin/bash"         2 weeks ago         Exited (255) 9 days ago                       naughty_poitras
```

- Start the container:

```bash
RedAdmin@Jump-Box-Provisioner:~$ sudo docker container start naughty_poitras
naughty_poitras
RedAdmin@Jump-Box-Provisioner:~$
```

- Connect to the Ansible container:

```bash
RedAdmin@Jump-Box-Provisioner:~$ sudo docker container attach naughty_poitras
root@b911d440b690:~#
```

- Copy the SSH key from the Ansible container on your jump box:

```bash

root@b911d440b690:~# cat ~/.ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCifGFl3FJ8BFDMkxOudiwuaD+8l4zjH10k62gLAPHgHs+fH7Y6qoVYxJMF+5QzA6esQ26fg5s/i8HKvZJZH7lfqc1IHspbRIBZKEeJ3IGB9vWMKgdAJKlSaWuMyFe8mJKyJSw8JcT4oRVjYe2jM8Ag05/nkAvjDRxEykjDW1MJob8DWasKRB1uePSJKR7sBXlFNCs6axURgzEZsk7MQdGFFX6uM1iqQLEztHOqV+5ShEANpAIEcjJsqGKAFlqg2XtktwtQmgPrwHWhRuWhGnJl1doXDZqUhAI5IUgvQ7TRnRLBcBmjkziXPKLFUrJbm+pHF4Fe+YqWiLGhqU1bSj0H root@b911d440b690
```

- Configure a new VM using that SSH key.
- Make sure this VM has at least 4 GB of RAM.
- Make sure it has a public IP address.
- Make sure it is added to your new vNet and create a new Security Group for it.

- Solutions:
![](/Images/ELK-vm-1.png)

![](/Images/ELK-vm-2.png)


## Launching and Exposing the Container

After Docker is installed, download and run the `sebp/elk:761` container.
- The container should be started with these published ports:
- `5601:5601`
- `9200:9200`
- `5044:5044`

Your Ansible output should resemble the output below and not contain any errors:

```bash
root@b911d440b690:/etc/ansible# ansible-playbook install-elk.yml

PLAY [Configure Elk VM with Docker] ****************************************************

TASK [Gathering Facts] *****************************************************************
ok: [10.1.0.4]

TASK [Install docker.io] ***************************************************************
changed: [10.1.0.4]

TASK [Install python3-pip] *************************************************************
changed: [10.1.0.4]

TASK [Install Docker module] ***********************************************************
changed: [10.1.0.4]

TASK [Increase virtual memory] *********************************************************
changed: [10.1.0.4]

TASK [Increase virtual memory on restart] **********************************************
changed: [10.1.0.4]

TASK [download and launch a docker elk container] **************************************
changed: [10.1.0.4]

TASK [Enable service docker on boot] **************************************
changed: [10.1.0.4]

PLAY RECAP *****************************************************************************
10.1.0.4                   : ok=1    changed=7    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

- SSH from your Ansible container to your ELK machine to verify the connection before you run your playbook.

- After the ELK container is installed, SSH to your container and double check that your `elk-docker` container is running.

Run `sudo docker ps`

```bash
sysadmin@ELK-Server:~$ sudo docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                                                                              NAMES
ae2062313e86        sebp/elk:761        "/usr/local/bin/star…"   13 days ago         Up 3 hours          0.0.0.0:5044->5044/tcp, 0.0.0.0:5601->5601/tcp, 0.0.0.0:9200->9200/tcp, 9300/tcp   elk
sysadmin@ELK-Server:~$
```

Solutions:
- [Ansible Configuration File](Files/ansible.cfg)
- [Ansible Hosts File](Files/hosts)
- [ELK Playbook](Files/install-elk.yml)


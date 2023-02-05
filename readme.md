Prerequisites
* ansible installed on the system
* remote server with ssh access [ user ssh-add-key root@serverip ]
* enable password authentification on in [ /etc/ssh/sshd_config ]
* python3 installed on remote host
* ip address of remote host for ansible host file

Usage
* if remote host user is root

ansible-playbook -i inventory/hosts init-server.yml -u root --become-pass

* if remote host is none root

step 1: ansible-playbook -i inventory/hosts init-server.yml -u <user> --ask-become-pass
step 2: provide ssh password

* if remote server has ssh key

step 1: ansible-playbook -i inventory/hosts init-server.yml -u root -f <location>/ssh_key.pem --become-pass
step 2: provide encrypted passphrase for ssh_key.pem


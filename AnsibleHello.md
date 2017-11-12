
### Prepare ssh on each server
```bash
adduser username
usermod -aG sudo username
sudo apt-get update && sudo apt-get install -y python
export LC_ALL="en_US.UTF-8"
export LC_CTYPE="en_US.UTF-8"
sudo dpkg-reconfigure locales
ssh-copy-id server
```

### Install Ansible
apt-add-repository ppa:ansible/ansible
apt-get update
sudo apt-get install -y ansible

### Validate Ansible
ansible --version

### Validate Ansible networking
ansible -m ping all

### Some ad-hoc commands
ansible -m shell -a 'hostname' all
ansible -m shell -a 'df -h' all
ansible -m shell -a 'whoami' all
ansible -m shell -b -K -a 'sudo echo 123' all

### Run playbook
ansible-playbook -K playbook.yml

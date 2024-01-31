# ansible-devops


Installation of Ansible in Ubuntu

# Add the Ansible PPA
sudo apt-add-repository ppa:ansible/ansible

# Update the package list
sudo apt-get update

# Install Ansible
sudo apt-get install ansible

# Check Ansbile Install or Not
ansible --version
ansible [core 2.15.9]
  config file = /etc/ansible/ansible.cfg
  
  configured module search path = ['/home/ubuntu/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  
  ansible collection location = /home/ubuntu/.ansible/collections:/usr/share/ansible/collections
  
  executable location = /usr/bin/ansible
  
  python version = 3.10.12 (main, Nov 20 2023, 15:14:05) [GCC 11.4.0] (/usr/bin/python3)
  
  jinja version = 3.0.3
  
  libyaml = True

  sudo vim /etc/ansible/hosts
  
  #[servers]

server1 ansible_host=172.31.9.82
server2 ansible_host=172.31.10.30
server3 ansible_host=172.31.5.96

[servers:vars]
ansible_ssh_private_key_file=/home/ubuntu/tokyo-yagi.pem
ansible_python_interpreter=/usr/bin/python3
ansible_user=ubuntu

ansible servers -m ping #ping the servers

#Check memory via ad-hock command (enter any command)
ansible servers -a "free -h" 
ansible servers -a "hostname"
---------------------------------------------------------------

#To Check inventory 
ansible-inventory --list
ansible-inventory --list -y 
----------------------------

#Playbook
ansible-playbook -v enter-playbook-name.yaml
:wq

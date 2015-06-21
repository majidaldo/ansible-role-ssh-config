ansible-role-ssh_config
===========================

Generate a ~/.ssh/config with your inventory (keep your old .ssh/config in backup)

Available on Ansible Galaxy : https://galaxy.ansible.com/list#/roles/3116

# Playbook example :
```
  ---
   - hosts: all
     sudo: no
     gather_facts: yes

   - hosts: localhost
     connection: local
     sudo: false
     roles:
      - ssh-config
```
# Notes
- You need to gather_facts of your hosts before the run the role in local
- You old .ssh/config is keep in backup and integrated to the new .ssh/config

# Inventory file sample
```
  # simple
  testserver ansible_ssh_host=10.0.0.2 ansible_ssh_user=root
  
  # via ssh tunnel
  testserver ansible_ssh_host=10.0.0.2 ansible_ssh_user=root ansible_ssh_proxy_command="ssh -W %h:%p root@10.0.0.1"
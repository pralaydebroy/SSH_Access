# ssh-access
Grant/Revoke SSH access to a group of instances to a user

### Use below given command to add new user and grant SSH access
ansible-playbook -i inventory.txt -e "action=grant" playbooks.yml

### Use below given command to grant SSH access to an existing user
ansible-playbook -i inventory.txt -e "action=grant" playbooks.yml --skip-tags=add

### Use below given command to revoke SSH access from a user
ansible-playbook -i inventory.txt -e "action=revoke" playbooks.yml --skip-tags=remove

### Use below given command to remove user, hence revoke SSH access as well
ansible-playbook -i inventory.txt -e "action=revoke" playbooks.yml


## Notes
 - Under [instances] group in inventory.txt hosts files please make sure to add IPs or DNS of target instances.
 - Update the varibale "user_name" and "user_des" as per requirements. You can add multiple values as well to run the action for mutiple users at a time.

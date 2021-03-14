# Description
This Ansible script will launch and configure a Nginx server(s) in AWS,
you need an AWS account to run it.

# Discussion
Any comment please add a Pull Request or email ccwu27(at)gmail.com

# Require
1. AWS account with Access Key ID, and Secret Access Key
2. AWS security group with port 22 and 80 open
3. AWS ssh private key file

# Usage
1. update 'group_vars/all/vault.yml' for vault_ec2_access_key and vault_ec2_secret_key

2. encrypt 'vault.yml' file by 'ansible-vault encrypt group_vars/all/vault.yml'

3. update 'group_vars/all/vars.yml' for ec2_region, key_name, ec2_security_group
   
4. put your AWS ssh private key file in this project directory,
   rename the file as 'sshkey.pem'

   Note:
     sshkey.pem file permission must be '400'

5. run the playbook by 'ansible-playbook --ask-vault-pass site.yml'

6. test nginx site by ' curl "instance IP address" '

   Note:
     ec2 instance(s) created will be tagged with name 'Demo'

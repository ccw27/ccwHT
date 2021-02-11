1. update 'group_vars/all/vault.yml' for vault_ec2_access_key and vault_ec2_secret_key

2. encrypt 'vault.yml' file by 'ansible-vault encrypt group_vars/all/vault.yml'

3. update 'group_vars/all/vars.yml' for ec2_region, key_name, ec2_security_group

   Note:
     the AWS security group must have port 22 and 80 opened

4. rename your AWS ssh private key file as file name 'sshkey.pem'

5. run the playbook by 'ansible-playbook --ask-vault-pass site.yml'

6. test nginx site by 'curl <instance IP address>'

   Note:
     ec2 instance(s) created will be tagged with name 'Demo'

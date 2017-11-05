# ApacheEC2
creating ec2 instance with apache using Ansible.

1)Clone this repo to your any directory 

2) Configure dynamic host inventary for ansible as mentioned bellow: 
https://aws.amazon.com/blogs/apn/getting-started-with-ansible-and-dynamic-amazon-ec2-inventory-management/

 a) Ansible is installed and has access to your Secret and Access key (via EC2 role or environment variable)
*****

vi ~/.boto

  [Credentials]
AWS_ACCESS_KEY_ID=KID...CWU
AWS_SECRET_ACCESS_KEY=3qv...DSP


 b) Ec2.py and Ec2.ini inventory scripts are downloaded in /etc/ansible and configured
 
https://raw.githubusercontent.com/ansible/ansible/devel/contrib/inventory/ec2.py
https://raw.githubusercontent.com/ansible/ansible/devel/contrib/inventory/ec2.ini
 
 
 c) ANSIBLE_HOSTS environment variable set
 export ANSIBLE_HOSTS=/etc/ansible/ec2.py
 export EC2_INI_PATH=/etc/ansible/ec2.ini
 
 
d)SSH agent is running (You can check with “ssh-add -L”)
   copy your .pem  file to ./ssh/ directory 
   ssh-agent bash 
   ssh-add ~/.ssh/keypair.pem 
   
  run playbook:
 ansible-playbook -i /etc/ansible/ec2.py site.yml 


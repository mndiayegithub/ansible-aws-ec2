## Ansible + Docker + AWS EC2 

Deploy a containerized Web application in AWS EC2 using Ansible and Docker.

# Description :

- In this repository, I have set up a containerized Web application deployed on in AWS EC2 instance using Ansible and Docker.
- This guide describe how to deploy our Webapp in an AWS EC2 instance with Ansible and Docker. The process involves creating an AWS Account (Free if possible), setting up an EC2 instance, installing Docker on the EC2 instance, configuring the EC2 instance and deploy our Web Application only WITH Ansible playbook.
 
# Prerequisites : 

- [Create an AWS Free Account](https://portal.aws.amazon.com/billing/signup?p=ft&c=hp&z=6 "Create an AWS Free Account")
- Basic knowledge of AWS EC2 and Ansible
- Create an SSH Key pair

# Dependencies : 

- Ansible version : **3.9** 

# Workflow of Ansible playbook : 

- Install pre-requisites packages on local machine 
- Create and configure an AWS Server
- Deploy the Web application
  * Create an Apache container
  * Deploy Webapp in EC2 target servers

# How to set it up in your local machine ?

- Clone this repository with : 
```
git clone https://github.com/mndiayegithub/ansible-aws-ec2.git
```
- Get your _**AWS_ACCESS_KEY**_ & _**AWS_SECRET_ACCESS_KEY**_ and update the variables into **secret.yml** :
``` 
aws_access_key: '1234'
aws_secret_access_key: 'abc'
```
Do not forget to vault secret.yml with `ansible-vault encrypt secret.yml`.

- Get your SSH Key pair and put it as _**ec2_key.pem**_.
- Run the Ansible playbook _**deploy.yml**_ :
  * `ansible-playbook deploy.yml --ask-vault-pass --tags` (for vaulted files)
  * `ansible-playbook deploy.yml --tags` (With vaulted files) 


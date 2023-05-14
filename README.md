# Automation to Deploy Coolstore App on JBoss EAP Servers and PostgreSQL

## Pre-Tasks

- Current automation uses a zip file that contains the JBoss EAP binaries that is more than 200 MB in size
- GitHub has a limit of 100 MB for file size
- The current approach is to make use of s3 bucket to store the binaries instead
- Hence as part of pre-req, user will need to download the zip [file](https://drive.google.com/file/d/1RPU3jn0gXKoo7RQzsbfiUK1ZRhbByWil/view?usp=share_link) and then upload to their s3 bucket

## Deploy and Configure PostgreSQL Server
- Update the vars in the `deploy_ec2_instances.yml` playbook and run the playbook to deploy the required EC2 instance
- Update inventory with the IP Address of the EC2 instance
- Update the vars in the `deploy_postgresql.yml` playbook and run the playbook to deploy and configure the PostgreSQL server

## Deploy and Configure JBoss Servers

- Update the vars in the `deploy_ec2_instances.yml` playbook and run the playbook to deploy the required EC2 instances
- Update inventory with the IP Addresses of the EC2 instances
- Update the vars in the `deploy_jboss_eap_server.yml` playbook and run the playbook to deploy the JBoss EAP servers
- Update the vars in the `deploy_coolstore_app.yml` playbook and run the playbook to deploy the coolstore application

## Deploy and Configure AWS Application Load Balancer (ALB)

- Update the vars in the `deploy_aws_application_lb.yml` playbook and run the playbook to deploy and configure the ALB
- Check that the coolstore application is running properly

## TODO
- Create workflow using Ansible Automation Platform for end-to-end automation

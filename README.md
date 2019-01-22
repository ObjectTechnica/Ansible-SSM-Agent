AWS-SSM
=========

AWS Systems Manager is a collection of capabilities for configuring and managing your Amazon EC2 instances, on-premises servers and virtual machines, and other AWS resources at scale. AWS Systems Manager Agent (SSM Agent) is Amazon software that runs on your Amazon EC2 instances and your hybrid instances that are configured for Systems Manager (hybrid instances). SSM Agent processes requests from the Systems Manager service in the cloud and configures your machine as specified in the request. SSM Agent sends status and execution information back to the Systems Manager service by using the EC2 Messaging service. If you monitor traffic, you will see your instances communicating with ec2messages.* endpoints

Requirements
------------

Ansible 
Access keys if outside aws (not receommeneded)
A control host in AWS with instance profile able to run your ansible plays.
ENCRYPT YOUR VARS FILE!!!


Role Variables
--------------

Role variables include apt-get for debian/ubuntu and yum for RHEL/CentOS AMI's.  This is handled by the gather_facts: true  Changing that to false could result in role variable errors

Roles can also be broken up by tag.  This is included when you only need to run one aspect of the Ansible role.


Example Playbook
----------------

Example 1) Drop and go
ansible-playbook -i inventory/aws-ssm.yml aws-ssm.yml --ask-vault-pass

Example 2) Running with tag "pre-flight"
ansible-playbook -i inventory/aws-ssm.yml aws-ssm.yml --ask-vault-pass -t pre-flight

Example 3) Running with tag "aws-ssm-run"
ansible-playbook -i inventory/aws-ssm.yml aws-ssm.yml --ask-vault-pass -t aws-ssm-run


License
-------

MIT

Author Information
------------------

Adam A. Valenzuela - Brevity is the Soul of Wit.

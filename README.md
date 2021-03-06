# Introduction to Ansible: From Playbook to Production
This is an example repo that shows how to use Ansible from the first playbook all the way through CI testing and production deployments.

The slides from a presentation on this repo can be found here:

https://speakerdeck.com/kday/introduction-to-ansible-from-playbook-to-production

# Requirements

There are both Python and Ruby requirements.

Install the Python requirements via pip:

`pip install -r requirements.txt`

Install the Ruby requirements via bundler:

`bundle install`


# Configuring Builds on Circle CI

1. Add AWS credentials on the "AWS Permissions" tab of the Project Settings page.
  * Using an IAM user is recommended.
  * The user must have access to create and destroy instances, and create tags and associate them with an instance.
1. Edit the key_name in build/provision-test-instance.yml to be a keypair owned by you.

# Building an Environment

## Create the database first
`ansible-playbook environments/prod/mysql-rds.yml -i inventory/pseudo_localhost`


# TODO
1. More documentation on configuration
1. More documentation on usage
1. Change provision-test-instance.yml playbook to use role from roles/infra

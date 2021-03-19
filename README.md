# MongoDB configured by Ansible
This role provides a means to install and confiugre MongoDB servers.

It supports a few scenarios out of the box:

* Local database without security features
* Network-reachable database with SSL and Authentication
* Replicated database (replicaset in MongoDB terms) with SSL and Authentication

In order to deploy a new MongoDB you need to do the following things:

* Include this role in your Ansible code
* Set the configuration you need (see defaults/main.yml)
* Run your playbook

If you require SSL, you need to provide the SSL certificate files before this role is run.

This role will take care of the following aspects (depending on configuration):

* Configuration of repositories
* Installation of software packages (PyPi or distro manager)
* Configuration files and directories
* MongoDB admin user
* TuneD configuration to set MongoDB recommended settings
* MongoDB Replica-set creation
* MongoDB users and databases creation

# Dependencies
To function, this role requires:

* Ansible collection: community.mongodb
* Python library: pymongo (see defaults/main.yml for a version table)

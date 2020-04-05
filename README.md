Deploy a Production Ready MongoDB Cluster using Ansible
=======================================================

This ansible playbook supports the following,

- Can be deployed on baremetal and VMs(AWS EC2)
- Supports most popular **Linux distributions**(Centos7, RHEL7)
- Install and configure the MongoDB in two methods, Replica Set cluster or Single node setup.
- TLS/SSL [Configuration](https://docs.mongodb.com/manual/tutorial/configure-ssl-clients/) for Clients communication.
- Configure [x.509](https://docs.mongodb.com/manual/core/security-internal-authentication/#x-509) certificate authentication for Internal(Node to Node) communication.
- Using self-signed certificates to configure TLS/SSL.
- Enable the Role-Based Access Control to govern access to a MongoDB Cluster.
- Create the Admin user with given credentials.

Requirements
------------
- **Ansible**
- **Java 8**

Configure
---------

Refer the configuration file `inventories/mongodb/test/group_vars/all/all.yml` to change the default configuration values.

Note: test - Environment name.

You can also change the MongoDB versions in configuration file.

You can change the admin username and  password using `mongodb_admin_user` and `mongodb_admin_password` variables.

Install
-------

### Ansible

    # Deploy with ansible playbook - run the playbook as root
    ansible-playbook -i inventories/mongodb/test/hosts mongodb.yml

Once the deployment has completed, you can access the mongodb cluster with user `admin` and password `Test123`(Default values).

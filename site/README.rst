##EC2

EC2play book

This playbook Launches an EC2 instance and assigns the ip address to the instance and install and enables the http service for that EC2 instance in AWS.

Description:
#- name: apply common configuration to (EC2 INSTANCE IP)
#  hosts: (EC2 INSTANCE IP)
#  remote_user: root

The above piece of yml script recognizes a ec2 instance IP and access the Instance as root user.

#- name: Installing httpd service
#  yum: name=httpd state=present

The above script installs the apache http service on the ec2 instance with yum package manager.


#template: src=/etc/ansible/index.html dest=/var/www/html

The http service will now look at index.html located at /var/www/html which is the source of /etc/ansible/index.html

# /etc/ansible/index.html file has the following content
 #<html>
 #  <head>
 #    <title>Hello World</title>
 #  </head>
 #  <body>
 #    <h1>Hello World!</h1>
 #  </body>
 #</html>

 Now Http service gives the Output as Hello World! in the web Browser for the particular instance IP.

Removing and Adding a Node

Removal and addition of nodes to the cluster is as simple as editing the hosts inventory and re-running:

             ansible-playbook -i hosts site.yml

Rolling Update

            ansible-playbook -i hosts rolling_update.yml




#site.yml will exist inside of the playbook folder and this is the playbook itself.

Ansible excutaion steps:

steps to apply this ansible playbook on a particular node:

* install Ansible on desired server(centos,redhhat) using the 'yum' command.
* Keys based SSH authentication with Nodes
* Creat Inventory of Remote Hosts.
* use the command ansible -m ping IP (to verfiy connectivity from from Ansible server to remote servers)
* Creating Playbooks in Ansible.Save and close the file and then create (source hello world) html file . PATH vi /etc/ansible/ index.html.
* Run the Playbook in Ansible  with following command ansible-playbook -l IP site.yml


 command to execute ansible playbook (site.yml) for a particular node.

	         ansible-playbook -l hosts site.yml


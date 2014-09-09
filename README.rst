jenkins-ansible
===============

Ansible Playbooks to Deploy Jenkins and required plugins on Redhat/Fedora/Centos
System. It will also create self-signed certificate and enable HTTPS/SSL for
jenkins at port 8443.

Configuration
=============

.. important:: 

  * Add your jenkins host to `hosts` file and make sure your control node have ssh-key pair setup.
  * Modify User details in `jenkins.yml` file, user should present in sudoers
  * If you add `root` user then put `sudo` as `no`
  * Check plugins section in `groups_vars/all` and add/remove required plugins


How to Run
==========

If you want allinone setup (jenkins install -> plugins install -> SSL enable)
please run below command. make sure ansible is installed your controler box. 

::

 ansible-playbook -i hosts jenkins.yml

 Sample Input
 ~~~~~~~~~~~~

 Alias Name: jenkins
 Domain/Company/First and Last Name, format should be 'CN=fedorproject.org, OU=ID, O=Fedora, L=Praveen, S=Kumar, C=DEV': 'CN=fedorproject.org, OU=ID, O=Fedora, L=Praveen, S=Kumar, C=DEV'
 keystore Name: keystore
 Enter password: 
 Enter key password: 


If you want to run a specific role then you can use role tag.

::
 
 ansible-playbook -i hosts -t setup jenkins.yml

 Above command only Install Jenkins and provided plugins, It will not setup SSL
 for current instance but it does ask same Input question because I didn't find
 a way to make `vars_prompt` as role specific.

TODO
====

* Create new role for Update/Install a plugin when Jenkins is present.
* Create new role for Slave add.

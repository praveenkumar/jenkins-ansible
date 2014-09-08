jenkins-ansible
===============

Ansible Playbooks to Deploy Jenkins and required plugins on Redhat/Fedora/Centos
System

How to run
==========

* Add your jenkins host to hosts file and make sure your control node have ssh-key pair setup.
* Modify User details in jenkins.yml file, user should present in sudoers

::

 ansible-playbook -i hosts jenkins.yml

 Provide asked UserInput to generate self-signed certificate.

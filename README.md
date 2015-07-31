Openstack-log.io
================

This project is a set of simple ansible playbooks to allow an Openstack operator to quickly and easily setup
log.io temporarily on a number of Openstack nodes, as a means of doing some real-time log collection and
debugging, in environments where centralised logging infrastructure does not exist.

Requirements
============

Currently this project relies on l3 connectivity between the server running the playbooks, and the Openstack
nodes themselves. In particular, firewalls should not block ports 28777 and 28778

Usage
=====

First run the download-and-prepare-files playbook like

    ansible-playbook download-and-prepare-files.yaml

Once that is complete you will have local copies of nodejs and log.io ready to be utilised.

Next, modify inventory/hosts, changing the entries under openstack-nodes to match those of your environment.
Finally run the openstack-log.io playbook

    ansible-playbook openstack-log.io.yaml

Remember that if you need a password to run sudo on the machine that will be running log.io, you will need
to run the playbook with the --ask-sudo-pass option

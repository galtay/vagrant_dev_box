# Automated Development Environment

This repo contains the files needed to setup a development environment on
a virtual machine using
[virtualbox](https://www.virtualbox.org/),
[vagrant](https://www.vagrantup.com/), and
[ansible](http://docs.ansible.com/ansible/index.html).
The most recent tests were done with,

    VirtualBox 5.0.2
    Vagrant 1.7.4
    Ansible 1.5.4


## Setup Virtual Machine

With the three pre-requisites installed, a virtual machine can be started
by giving the command,

    vagrant up

from the directory that contains the ``Vagrantfile``.  You can then connect
to the virtual machine using:

    vagrant ssh


## Setup Local Machine

It is also possible to provision a local machine using these files.
In order for these files to work locally, the ``remote_user`` variable in
the file ``provision/playbook.yaml`` should be changed from ``vagrant`` to
whatever username you are using on your local machine.  Then the playbook
can be run locally using the command,

    ansible-playbook -i inventory_local.ini -s -K provision/playbook.yaml
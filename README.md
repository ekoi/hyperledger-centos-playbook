## Hyperledger on CentOS7

This repository contains a Vagrantfile that spins up a CentOS7 box and uses an Ansible playbook to provision this VM. This Ansible playbook could be used to provision any related OS.

## Getting started

Make sure Vagrant, VirtualBox and Ansible are on your computer. Use your system's package manager or install the binaries.

See:
  * https://www.vagrantup.com/intro/getting-started/install.html
  * https://www.virtualbox.org/wiki/Downloads
  * http://docs.ansible.com/ansible/latest/intro_installation.html

## Spin up Hyperledger

Simply navigate to the root of this project and issue the command:

`vagrant up`

This will first download a clean CentOS7 image, that will take some time. After this the VM is started and the Ansible playbook is executed against this machine. This will install all of the necessary components described in:

  * https://hyperledger.github.io/composer/installing/installing-prereqs
  * https://hyperledger.github.io/composer/installing/development-tools.html

## Usefull Vagrant commands

To pause the box: `vagrant halt`
To resume a halted box: `vagrant resume`
To destroy a box: `vagrant destroy`
To re-provision: `vagrant provision`

See for a complete overview: https://www.vagrantup.com/docs/cli/

## Accessing the Hyperledger box

The CentOS VM is started with a private network setup. Accessing application via a browser: `http://192.168.42.42:<port>`

## Running Ansible

As mentioned earlier, the playbook can be executed against any related OS. Issue the command: `ansible-playbook -i <target-host>, playbook-hyperledger.yml`

Networking depends on the target machine and is not managed by the playbook and should be handled manually if required.


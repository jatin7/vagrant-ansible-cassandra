##Introduction

Easily provision 3 DSE Cassandra 4.6 nodes and Opscenter 5.0 across 4 VMs using Ansible with Vagrant & Virtualbox.

##Prerequisites

* [Virtualbox](https://www.virtualbox.org/)
* [Vagrant](https://www.vagrantup.com/downloads)
* [Ansible](http://docs.ansible.com/intro_installation.html)

Add the Ubuntu 12.04 vagrant base image: ```vagrant box add precise64 http://files.vagrantup.com/precise64.box```

##Provisioning

Clone the project: ```git clone https://github.com/joeljacobson/vagrant-ansible-dse-cluster.git```

In the project directory enter: ```vagrant up```

Your cluster will be ready shortly depending on your internet connection. The initial boot takes some time as Ansible has to download, setup and configure DSE across each VM. Subsequent reboots are fast.

DSE and Opscenter will be automatically configured and started once installed. They will also be automatically started each time the VMs are booted.

Nodes will be running on: ```192.168.56.10```, ```192.168.56.20```, ```192.168.56.30```

Opscenter will be running on: ```192.168.56.40:8888```

Install the datastax-agents by entering ```vagrant``` for both the username and password.

SSH into a node with: ```vagrant ssh <nodename>```

Shutdown the VMs: ```vagrant halt```

Resume VMs: ```vagrant up```

Destroy the VMs (requires re-provisioning): ```vagrant destroy```

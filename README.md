# ADTsys ansible deploy
Automation Project to deploy ADTsys application test using Ansible playbooks on a Vagrant instance
## Introduction

### Architecture
This application instantiate a Vagrant virtual machine using Ansible as
provisioner to build a Rails test/development/production isolated environment and clones the git repo that contain the solution for this test.  
It is required to have both Vagrant and Ansible installed.  
Install instructions can be found here:
* Vagrant install instructions:
    * [Vagrant instructions](https://www.vagrantup.com/docs/installation/)
* Ansible install instructions:
    * [Ansible instructions](http://docs.ansible.com/ansible/intro_installation.html)  

*(For Mac Os X it is recommended to use homebrew to  install Ansible)*

Once this packages are installed the next steps are:  

**1. Instructions**

* Clone the repo ([Source Code](git@github.com:havk64/ADTsys-ansible-deploy.git))  

* On command line:

        $ cd ADTsys-ansible-deploy
* And run:

        $ vagrant up

> *(It will take sometime to download and install all components for the first time. Grab a cup of coffee ;-) )*  

Once the installation is finished, open your browser and point it to [**localhost:5000/**](localhost:5000/) to see the app running.  
You can always run `vagrant ssh` in order to login to the vagrant machine.  
The ansible tasks were built to be **idempotent**, that is, you can provision the virtual machine with related ansible tasks how many times you want without compromising the system or have duplicated files or configuration, following practices for CI/CD(Continuous Integration, Continuous Delivery).  
If for some reason the installation process stops just run again `vagrant up`(to initialize the machine) or `vagrant provision`(if the machine is already up and running) to re-run all tasks again.  
At the end you can run `vagrant destroy` to delete the virtual machine and its components.


---------------

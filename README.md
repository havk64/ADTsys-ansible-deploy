# ADTsys ansible deploy
Automation Project to deploy ADTsys application test using Ansible on a Vagrant instance
## Introduction

### Architecture
This application instantiate a Vagrant virtual machine using Ansible as
provisioner to build a Rails development/production isolated environment.  
It is required to have both Vagrant and Ansible installed.
Install instructions can be found here:
* Vagrant install instructions:
    * [Vagrant instructions](https://www.vagrantup.com/docs/installation/)
* Ansible install instructions:
    * [Ansible instructions](http://docs.ansible.com/ansible/intro_installation.html)  

*(For Mac Os X it is recommended to use homebrew to  install Ansible)*

Once this packages are installed the next steps are simple:  

**1. Instructions**

* Clone the repo ([Source Code](git@github.com:havk64/ADTsys-ansible-deploy.git))  

* On command line:  
        $ cd ADTsys-ansible-deploy
* And run:
        $ vagrant up

> *(It will take sometime to download and install all components for the first time. Grab a cup of coffee ;-) )*  

Once it is finished, open your browser and point it to [**localhost:5000/**](localhost:5000/) to see the app running.
You can always `vagrant ssh` in order to login to the vagrant machine.  
This environment and Ansible tasks were built to be idempotent, that is, you can provision the virtual machine how many times you want without compromising the system or have duplicated files or configuration.  
If for some reason the process stops just run `vagrant up` again or `vagrant provision`(if the machine is already up) to re-run all tasks again.

### About the application
This Web Application is written in Ruby using Ruby on Rails using PostgreSQL for persistence.  
The front end was not priority in order to focus on the ruby code and on minimize the database requests.  
For that matter I used some control flow checks that ensure that requests to update the database using the Webmotors API are made just when new items are added, so on each request for the page(client request) just one request is sent to the database.
Also, if the Webmotors API is not available for some reason the application don't stop working and can keep serving pages using its persisted data.
All code needed to make the requests for the API were moved to a ***[Service Object]()*** in order to keep the controllers and models clean and DRY.    

by Alexandro de Oliveira
---------------

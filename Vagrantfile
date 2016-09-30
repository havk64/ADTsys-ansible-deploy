# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb|
    vb.name = "ADTsys-ansible"
    vb.memory = 1024
  end
  config.vm.network "forwarded_port", guest: 3000, host: 5000
  config.vm.hostname = "rails-postgres"
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.inventory_path = "hosts"
    ansible.playbook = "site.yml"
  end
end

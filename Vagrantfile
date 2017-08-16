# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.


  config.vm.box = "debian/stvaretch64"
 # config.vm.box = "ubuntu/xenial64"

  config.vm.provider :virtualbox do |v|
     v.name = "snuffles.dev"
     v.memory = 2048
     v.cpus = 2
   end 

  config.vm.provision :ansible do |ansible|
      #  ansible.verbose = "vvv"
        ansible.playbook = "playbook.yml"
          ansible.inventory_path = ".vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory"
    end

end

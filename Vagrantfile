# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.


 # config.vm.box = "debian/stvaretch64"
  config.vm.box = "ubuntu/xenial64"

# Set the default hostname for this ubuntu box
  config.vm.hostname = "gitlab"

# Configigure Port Forwarding for GitLab  
  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.provider :virtualbox do |v|
     v.name = "gitlab.dev"
     v.memory = 2048
     v.cpus = 2
   end 

  config.vm.provision :ansible do |ansible|
        # ansible.verbose = "vvv"
        ansible.playbook = "gitlab.yml"
          ansible.inventory_path = ".vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory"
          ansible.raw_arguments  = "--ask-vault-pass"
    end

end

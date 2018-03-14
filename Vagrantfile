# -*- mode: ruby -*-
# vi: set ft=ruby :



# General project settings
#################################
ip_address = "172.22.22.22"
project_name = "cli"



# Vagrant configuration
#################################

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  
  config.berkshelf.enabled = false


    config.hostmanager.enabled = true
    config.hostmanager.manage_host = true
    config.vm.define project_name do |node|
    node.vm.hostname = project_name + ".local"
      config.vm.network "public_network", bridge: [ "Realtek USB GbE Family Controller" ]
    end
    config.vm.provision :hostmanager


    config.vm.provision :shell, :inline => "sudo curl -L https://www.opscode.com/chef/install.sh | sudo bash"
    

    # Enable and configure chef solo
    #config.vm.provision :chef_solo do |chef|
    #end


  end
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
  # Create the management node
  config.vm.define :mgmt do |mgmt_config|
    mgmt_config.vm.box = "bento/ubuntu-16.04"
    mgmt_config.vm.hostname = "mgmt"
    mgmt_config.vm.network :private_network, ip: "10.0.15.10"
    mgmt_config.vm.provider "virtualbox" do |vb|
      # Customize the amount of memory on the VM:
      vb.memory = 256

      # Customize the number of CPUs on the VM:
      vb.cpus = 1
    end
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y software-properties-common
    apt-add-repository ppa:ansible/ansible
    apt-get update
    apt-get install -y ansible
  SHELL
end

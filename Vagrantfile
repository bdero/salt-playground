# -*- mode: ruby -*-
# vi: set ft=ruby :

salt_master_address = 2

Vagrant.configure(2) do |config|
  # Create the salt master
  config.vm.define :salt do |node|
    node.vm.box = "ubuntu/trusty64"
    node.vm.network "private_network", ip: "10.100.0.#{salt_master_address}"
    node.vm.provision :hosts, :sync_hosts => true
  end
  # Create the salt minions
  (1..3).each do |num|
    config.vm.define "minion#{num}" do |node|
      node.vm.box = "ubuntu/trusty64"
      node.vm.network "private_network", ip: "10.100.0.#{salt_master_address + num}"
      node.vm.provision :hosts, :sync_hosts => true
    end
  end
end

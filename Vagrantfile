# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define :salt do |node|
    node.vm.box = "ubuntu/trusty64"
    node.vm.network "private_network", ip: "10.100.0.2"
    node.vm.provision :hosts, :sync_hosts => true
  end
  (1..3).each do |num|
    config.vm.define "minion#{num}" do |node|
      node.vm.box = "ubuntu/trusty64"
      node.vm.network "private_network", ip: "10.100.0.3"
      node.vm.provision :hosts, :sync_hosts => true
    end
  end
end

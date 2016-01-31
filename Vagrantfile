# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "salt" do |salt|
    salt.vm.box = "ubuntu/trusty64"
    salt.vm.network "private_network", ip: "10.100.0.0"
  end
  config.vm.define "minion" do |minion|
    minion.vm.box = "ubuntu/trusty64"
    minion.vm.network "private_network", ip: "10.100.0.1"
  end
end

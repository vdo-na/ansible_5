# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"

  config.vm.define "vm1" do |vm1|
    vm1.vm.hostname = "web-node-1"
    vm1.vm.network "private_network", ip: "192.168.56.10"
    
    vm1.vm.synced_folder "./shared", "/home/vagrant/shared", type: "virtualbox"
    vm1.vm.provision "file", source: "./provision_test.txt", destination: "/home/vagrant/provision_test.txt"
  end

  config.vm.define "vm2" do |vm2|
    vm2.vm.hostname = "web-node-2"
    vm2.vm.network "private_network", ip: "192.168.56.11"
    
    vm2.vm.synced_folder "./shared", "/home/vagrant/shared", type: "virtualbox"
    vm2.vm.provision "file", source: "./provision_test.txt", destination: "/home/vagrant/provision_test.txt"
  end

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 1
  end
end
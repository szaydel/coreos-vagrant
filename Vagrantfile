# -*- mode: ruby -*-
# # vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "coreos"
  config.vm.box_url = "http://storage.core-os.net/coreos/amd64-generic/dev-channel/coreos_production_vagrant.box"
  config.vm.provider "virtualbox" do |vb|
    vb.customize ["storagectl", :id, "--name", "SATA", "--hostiocache", "on"]
    vb.customize ["storageattach", :id, "--storagectl", "SATA", "--port", "0", "--nonrotational", "on"]
    vb.customize ["storageattach", :id, "--storagectl", "SATA", "--port", "0", "--discard", "on"]
    vb.customize ["modifyvm", :id, "--cpuexecutioncap", "25"]
    vb.customize ["modifyvm", :id, "--hwvirtex", "on"]
    vb.customize ["modifyvm", :id, "--nictype1", "virtio"]
    vb.customize ["modifyvm", :id, "--nictype2", "virtio"]
    vb.customize ["modifyvm", :id, "--nic1", "nat"]
    vb.customize ["modifyvm", :id, "--nic2", "hostonly"]
    vb.customize ["modifyvm", :id, "--hostonlyadapter2", "vboxnet2"]
  end
end

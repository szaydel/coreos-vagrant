# -*- mode: ruby -*-
# # vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "coreos"
  config.vm.box_url = "http://storage.core-os.net/coreos/amd64-generic/dev-channel/coreos_production_vagrant.box"
  # Fix docker not being able to resolve private registry in VirtualBox
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
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

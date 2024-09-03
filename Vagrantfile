# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_SERVER_URL'] = 'https://vagrant.elab.pro'

Vagrant.configure(2) do |config|
    config.vm.box = "ubuntu/jammy64"
    config.vm.synced_folder ".", "/vagrant"
    config.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 1
    end
    (0..1).each do |i|
        config.vm.disk :disk, size: "10GB", name: "disk-#{i}"
    end 
    config.vm.define "grub" do |grub|
      grub.vm.network "private_network", ip: "192.168.50.10", virtualbox__intnet: "net1"
      grub.vm.hostname = "grub"
    end
 
  end
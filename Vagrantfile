# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "generic/centos7"
  config.vm.define "droste-1"
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox", SharedFoldersEnableSymlinksCreate: false
  config.ssh.insert_key = false
  config.vm.provider "virtualbox" do |vb|
    vb.name = "droste-1"
    vb.memory = 8192
    vb.customize ["modifyvm", :id, "--nested-hw-virt", "on"]
    vb.customize ["modifyvm", :id, "--ioapic", "on"]
    vb.customize ["modifyvm", :id, "--usbohci", "off"]
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "droste.yml"
  end
end

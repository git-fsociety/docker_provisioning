# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/buster64"
  config.vm.box_check_update = false
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

  (1..4).each do |i|
    config.vm.define "node#{i}" do |node|
      node.vm.hostname = "node#{i}"
      node.vm.network "public_network", ip: "10.0.0.12#{i}", bridge: "wlp1s0"
      node.vm.provision "ansible" do |ansible|
        ansible.playbook="provisioning.yml"
      end
    end
  end
end

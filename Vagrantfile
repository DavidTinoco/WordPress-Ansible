# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  config.vm.define :nodo1 do |nodo1|
      nodo1.vm.box = "debian/stretch64"
      nodo1.vm.hostname = "nodo1"
      nodo1.vm.network "private_network", ip: "10.0.0.12", virtualbox__intnet: "network"
      nodo1.vm.network "private_network", ip: "172.16.0.100"
      nodo1.vm.synced_folder '.', '/vagrant', disabled: true
      nodo1.vm.box_check_update = false
      nodo1.vm.provision "ansible" do |ansible|
        ansible.inventory_path = "hosts.ini"
        ansible.playbook = "pbnodo1.yml"
      end
  end
  config.vm.define :nodo2 do |nodo2|
      nodo2.vm.box = "debian/stretch64"
      nodo2.vm.hostname = "nodo2"
      nodo2.vm.network "private_network", ip: "10.0.0.13", virtualbox__intnet: "network"
      nodo2.vm.network "private_network", ip: "172.16.0.69"
      nodo2.vm.synced_folder '.', '/vagrant', disabled: true
      nodo2.vm.box_check_update = false
      nodo2.vm.provision "ansible" do |ansible|
        ansible.inventory_path = "hosts.ini"
        ansible.playbook = "pbnodo2.yml"
      end
  end
end

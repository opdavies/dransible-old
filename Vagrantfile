# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/ubuntu1604"
  config.vm.hostname = "dransible"
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provider "virtualbox" do |vb|
    vb.name = 'dransible'
    vb.memory = 2048
    vb.cpus = 1
  end

  # Set the name of the VM. See: http://stackoverflow.com/a/17864388/100134
  config.vm.define :dransible do |dransible|
  end

  config.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "ansible/provision.yml"
    ansible.inventory_path = "ansible/hosts.yml"
    ansible.become = true
    ansible.ask_vault_pass = true
  end

end

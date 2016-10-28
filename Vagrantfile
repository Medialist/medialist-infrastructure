# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "dev.medialist.io"
  config.vm.network "private_network", ip: "10.100.106.100"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.inventory_path = "dev/inventory"
    ansible.playbook = "bootstrap.yml"
    ansible.limit = 'all'
    ansible.ask_vault_pass = true
    ansible.extra_vars = {
      ansible_user: "vagrant"
    }
  end
end

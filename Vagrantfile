# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "debian/jessie64"
  config.vm.network :private_network, ip: "192.168.66.6"
  config.vm.hostname = "owncloud"
  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.memory = 1024
#    v.gui = true
  end

  # Ansible provisioning.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.sudo = true
  end
end

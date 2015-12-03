# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.network :private_network, ip: "192.168.33.34"
  config.vm.define "flowbat" do |flowbat|
    flowbat.vm.box = "ubuntu/trusty64"
    flowbat.vm.provision "ansible" do |ansible|
      ansible.extra_vars = { ansible_ssh_user: 'vagrant'
      }
      ansible.playbook = "main.yaml"
    end
  end

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--memory", "1024"]
  end

end
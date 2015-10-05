# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "vagrantbox" do |vagrantbox|
    vagrantbox.vm.box = "ubuntu/trusty64"
    vagrantbox.vm.network "private_network", ip: "192.168.15.101"
    vagrantbox.vm.hostname = "vagrantbox"
    config.vm.provision "shell",
      inline: "apt-get update && apt-get install python-software-properties -y && apt-get install software-properties-common -y && apt-add-repository ppa:ansible/ansible && apt-get update && apt-get install ansible -y && cp /vagrant/hosts /etc/ansible/hosts"
    if Vagrant.has_plugin?("vagrant-ansible-local")
      config.vm.provision "ansibleLocal", playbook: "playbook.yml"
    else
      config.vm.provision "shell",
        inline: "ansible-playbook /vagrant/playbook.yml"
    end
  end
end

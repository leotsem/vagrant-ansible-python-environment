# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "goldstein/centos7"
  
  config.vm.network "private_network", ip: "16.16.16.16"
  config.vm.network "forwarded_port", guest: 80, host: 80
  
  config.vm.synced_folder ".", "/data/www/playground"
  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/vagrant.yml"
    ansible.limit = "all"
  end

end
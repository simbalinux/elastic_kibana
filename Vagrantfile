# -*- mode: ruby -*-
# vi: set ft=ruby :
    
Vagrant.configure(2) do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = 4000
    v.cpus = 2
  end
#  config.vbguest.auto_update = true
  config.vm.define  "elkmaster" do |host|
    host.vm.box = "centos/7"
    host.vm.hostname = "stat.example"
    host.vm.network "private_network", ip: "192.168.50.63"
    host.vm.provision "shell", path: "strap_elk"
    host.vm.network "forwarded_port", guest: 9200, host: 9200
    host.vm.network "forwarded_port", guest: 5601, host: 5601 
  end
end



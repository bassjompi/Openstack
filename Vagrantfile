# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|


 config.vm.provision :shell, :inline => "ulimit -n 8048"
 config.vm.define "controller" do |controller|
   controller.vm.box = "centos/7"
   controller.vm.hostname = "controller"
   controller.vm.network "private_network", ip: "192.168.33.13", :netmask => "255.255.255.0"
   controller.vm.network "private_network", ip: "172.29.236.13", :netmask => "255.255.255.0"
   controller.vm.provision :ansible do |ansible|
   ansible.playbook = "playbook.yml"
  end
   controller.vm.provider "virtualbox" do |pmv|
      pmv.memory = 3072
    end
    end
 config.vm.define "compute1" do |compute1|
    compute1.vm.box = "centos/7"
    compute1.vm.hostname = "compute1"
    compute1.vm.network "private_network", ip: "192.168.33.14", :netmask => "255.255.255.0"
    compute1.vm.network "private_network", ip: "172.29.236.14", :netmask => "255.255.255.0"
    compute1.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook_compute.yml"
  end
compute1.vm.provider "virtualbox" do |pmv|
      pmv.memory = 3072
    end
    end


end

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "serv1" do | serv1|
    serv1.vm.box = "centos/7"
    serv1.vm.network "private_network", ip: "192.168.33.11"
    serv1.vm.hostname = "serv1"
    serv1.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--name", "serv1"]
      vb.memory = "1024"
    end
    serv1.vm.provision "shell", inline: <<-SHELL
      sudo useradd ansible  
      SHELL
  end
  config.vm.define "serv2" do | serv2|
    serv2.vm.box = "centos/7"
    serv2.vm.network "private_network", ip: "192.168.33.12"
    serv2.vm.hostname = "serv2"
    serv2.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--name", "serv2"]
      vb.memory = "1024"
    end
    serv2.vm.provision "shell", inline: <<-SHELL
      sudo useradd ansible  
      SHELL
  end
  config.vm.define "master" do | master|
    master.vm.box = "centos/7"
    master.vm.network "private_network", ip: "192.168.33.10"
    master.vm.hostname = "master"
    master.vm.provider "virtualbox" do |vb|
      vb.customize ["modifyvm", :id, "--name", "master"]
      vb.memory = "1024"
    end
    master.vm.provision "shell", inline: <<-SHELL
    sudo yum install epel-release -y
    sudo yum install ansible -y
    sudo useradd ansible
    SHELL
  end
end
# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "controlnode" do |controlnode|
    controlnode.vm.box = "zhekazuev/ubuntu-20.10"
    controlnode.vm.box_version = "1.0.0"
    controlnode.vm.hostname = "controlnode"
    controlnode.vm.network "private_network", ip: "192.168.50.4"
    controlnode.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 1
    end
    controlnode.vm.synced_folder "./ansible","/home/vagrant/ansible"
    controlnode.vm.provision "shell", inline: <<-SHELL
      sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/#g' /etc/ssh/sshd_config
      service ssh restart
    SHELL
  end

  config.vm.define "server" do |server|
    server.vm.box = "zhekazuev/ubuntu-20.10"
    server.vm.box_version = "1.0.0"
    server.vm.hostname = "server"
    server.vm.network "private_network", ip: "192.168.50.5"
    server.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 1
    end
    server.vm.provision "shell", inline: <<-SHELL
      sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/#g' /etc/ssh/sshd_config
      service ssh restart
    SHELL
   end
end

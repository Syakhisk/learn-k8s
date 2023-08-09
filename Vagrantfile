# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/jammy64"

  # config.vm.network "forwarded_port", guest: 22, host: 2222
  # config.ssh.username = "vagrant"
  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.linked_clone = true
  end

  # # config.vm.provision "shell", inline: <<-SHELL
  # #   apt-get update
  # # SHELL

  config.vm.define "master" do |config|
    config.vm.hostname = "master"
    config.vm.network "private_network", ip: "192.168.56.10"

    config.vm.provider "virtualbox" do |vb|
      vb.name = "k8s-master"
      vb.memory = "2048"
      vb.cpus = 2
    end
  end

  config.vm.define "worker" do |config|
    config.vm.hostname = "worker"
    config.vm.network "private_network", ip: "192.168.56.11"

    config.vm.provider "virtualbox" do |vb|
      vb.name = "k8s-worker-0"
      vb.memory = "2048"
      vb.cpus = 1
    end
  end
end

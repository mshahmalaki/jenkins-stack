# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'

Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |vbox|
    vbox.memory = 4096
    vbox.cpus = 4
  end
  config.vm.provider "libvirt" do |vbox|
    vbox.memory = 4096
    vbox.cpus = 4
  end
  config.vm.box = "generic/ubuntu2004"
  config.vm.hostname = "ubuntu"
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 50000, host: 50000
  config.vm.network "forwarded_port", guest: 443, host: 443
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 2222, host: 2233
  config.vm.network "forwarded_port", guest: 9000, host: 9000
  config.vm.network "forwarded_port", guest: 9001, host: 9001
  config.vm.synced_folder "jenkins-stack-docker/", "/home/vagrant/jenkins-stack-docker", type: "rsync"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
  config.vm.provision "shell", inline: <<-SHELL
    cd /home/vagrant/jenkins-stack-docker
    ./deploy
  SHELL
end
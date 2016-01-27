# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.require_version ">= 1.7.0"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "docker-host"

  config.vm.provider "virtualbox" do |virtualbox|
    virtualbox.memory = 2048
    virtualbox.cpus = 2
  end

  config.ssh.insert_key = false
  config.ssh.forward_agent = true

  config.vm.box_check_update = false
  config.vm.synced_folder ".", "/vagrant"

  config.vm.provision :docker
  config.vm.provision :docker_compose, yml: "/vagrant/compose/docker-compose.yml", rebuild: true, run: "always"
end

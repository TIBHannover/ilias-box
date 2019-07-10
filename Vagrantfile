# coding: utf-8
# -*- mode: ruby -*-
# vi: set ft=ruby :

# Configuration variables.
VAGRANTFILE_API_VERSION = "2"


DOMAIN  = 'ilias'
name = 'ilias-box'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.ssh.insert_key = true


    config.vm.define name do |machine|
      machine.vm.box = 'debian/stretch64'
      machine.vm.box_version = "9.8.0"

      machine.vm.provider "virtualbox" do |vbox|
        vbox.gui    = true
        vbox.cpus   = 2
        vbox.memory = 4096
        vbox.name   = name
      end

      machine.vm.hostname = name + DOMAIN
      machine.vm.network "private_network",  ip: "192.168.10.5"
      machine.vm.provision "shell", inline: "sudo timedatectl set-timezone Europe/Amsterdam", run: "always"
      machine.vm.provision "ansible" do |ansible|
          ansible.playbook = "ansible/ilias-playbook.yml"
          ansible.verbose = "vvv"
        end

    end


end
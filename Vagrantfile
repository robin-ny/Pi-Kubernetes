# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "debian/bookworm64"
    config.ssh.insert_key = false
    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.provider :libvirt do |libvirt|
        libvirt.memory = 2048
        libvirt.cpus = 2
    end

    config.vm.define "server" do |server|
        server.vm.network "private_network", ip: "192.168.42.42"
        server.vm.hostname = "server.local"
    end

    config.vm.define "agent" do |agent|
        agent.vm.network "private_network", ip: "192.168.42.43"
        agent.vm.hostname = "agent.local"
    end

  end
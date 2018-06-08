# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # General Vagrant VM configuration.
  config.vm.box = "ubuntu/trusty64"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider :virtualbox do |v|
    v.memory = 65536
    v.linked_clone = true
  end

  # Application server 1.
  config.vm.define "demo1" do |app|
    app.vm.hostname = "orc-app1.dev"
    app.vm.network :private_network, ip: "192.168.60.11"
  end

  # Application server 2.
  config.vm.define "demo2" do |app|
    app.vm.hostname = "orc-app2.dev"
    app.vm.network :private_network, ip: "192.168.60.12"
  end
end

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", 2048]
  end
  (1..3).each do |i|
    config.vm.define "node-#{i}" do |app|
      app.vm.hostname = "centos7"
      app.vm.box = "centos/7"
      app.vm.network :private_network, ip: "192.168.60.10#{i}"
    end
  end
end

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = 'bento/ubuntu-16.04'
  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |vb|
    vb.memory = 256
  end

  config.vm.define :web1 do |app|
    app.vm.network :forwarded_port, guest: 80, host:8080
    app.vm.provision :shell, path: 'provisioners/bash-script/install-apache2.sh'
  end
end

# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "bento/ubuntu-16.04"


  config.vm.provider :virtualbox do |vb|
    vb.memory = 256
  end

  config.vm.define :web1 do |w1|
    w1.vm.network :forwarded_port, guest: 80, host: 8080
    w1.vm.provision :shell, path: 'provisioners/web1/install_web1.sh'
  end

  config.vm.define :web2 do |w2|
    w2.vm.network :forwarded_port, guest: 80, host: 8081
    w2.vm.provision :shell, path: 'provisioners/web2/install_web2.sh'
  end

  config.vm.define :db do |db|
    db.vm.network :forwarded_port, guest: 80, host: 8082
    db.vm.provision :shell, path: 'provisioners/db/install_db.sh'
  end


end

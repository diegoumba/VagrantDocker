# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

$python36 = <<SCRIPT
sudo apt-add-repository ppa:jonathonf/python-3.6
sudo apt-get update
sudo apt-get install python3.6 -y
SCRIPT

$docker = <<SCRIPT
sudo apt-get install \
  linux-image-extra-$(uname -r) \
  linux-image-extra-virtual
curl -fsSL get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
SCRIPT

$redsocks = <<SCRIPT
sudo apt-get install redsocks -y
SCRIPT

Vagrant.configure(2) do |config|
  config.hostmanager.enabled = true
  config.vm.box = "ubuntu/xenial64"

  config.vm.define "d1appvagdoc01", primary: true do |h|
    h.vm.network  "public_network", :bridge => 'enp0s31f6', \
    :use_dhcp_assigned_default_route => true
    h.vm.hostname = "D1APPVAGDOC01"
    config.vm.provision "shell", inline: $docker
    config.vm.provision "shell", inline: $python36
    config.vm.provision "shell", inline: $redsocks
  end




end

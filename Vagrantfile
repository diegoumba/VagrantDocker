# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"

  config.vm.define "d1appvagdoc01", primary: true do |h|
    h.vm.network  "public_network", :bridge => 'enp0s31f6', \
    :use_dhcp_assigned_default_route => true
    h.vm.hostname = "D1APPVAGDOC01"
  end



end

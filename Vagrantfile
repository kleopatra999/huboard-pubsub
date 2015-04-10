# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "puppetlabs/ubuntu-14.04-64-puppet"

  config.vm.synced_folder ".", "/srv/huboard-pubsub", type: "nfs"
  config.vm.network "private_network", ip: "192.168.50.12"

  config.vm.network "forwarded_port", guest: 80, host: 9394 

  config.vm.provision "puppet", :module_path => [ "puppet/modules","modules" ] do |puppet|
    puppet.manifests_path = "puppet/manifests"
    puppet.manifest_file  = "base.pp"
  end
end

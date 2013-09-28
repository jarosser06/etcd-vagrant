# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "opscode-ubuntu-1204"
  config.vm.box_url = "https://opscode-vm-bento.s3.amazonaws.com/vagrant/opscode_ubuntu-12.04_provisionerless.box"
  config.berkshelf.enabled = true
  config.omnibus.chef_version = :latest

  config.vm.network :forwarded_port, guest: 4001, host: 4001
  config.vm.network :forwarded_port, guest: 7001, host: 7001

  config.vm.provision :chef_solo do |chef|
    chef.add_recipe "etcd"
  end
end

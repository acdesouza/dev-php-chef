# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.require_version ">= 1.5.0"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.hostname = "dev-php-berkshelf"
  config.vm.box = "ubuntu/trusty64"
  config.vm.network :private_network, type: "dhcp"

  config.omnibus.chef_version = :latest

  config.berkshelf.enabled = true

  config.vm.provision :chef_solo do |chef|
    chef.custom_config_path = "Vagrantfile.chef"

    chef.add_recipe "apt"
    chef.add_recipe "rvm::vagrant"
    chef.add_recipe "rvm::user" # RVM pra um user
    chef.add_recipe "nginx::default"
    chef.add_recipe "php-fpm"

    chef.json = {
      :rvm => {
        :user_installs => [
          {
            :user => "vagrant",
            :default_ruby => "2.1.2",
            :rubies => ["2.1.2"],
            :global_gems => [
              { :name => 'bundler' }
            ]
          }
        ],
        vagrant: {
          system_chef_solo: "/opt/chef/bin/chef-solo"
        }
      }
    }
  end
end

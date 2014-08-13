# EasyFood Developer PHP Box

Vagrant box created for PHP Developers at EasyFood

After git clone use:

```bash
vagrant up
```

Should create VirtualBox machine and provision with Nginx, PHP-Fmp, MySQL and RVM(for capistrano deploy).

## Box creation tools

  * [Vagrant](http://www.vagrantup.com/)
  * [Chef](http://downloads.getchef.com/chef-dk/)
  * [Berkshelf](http://berkshelf.com/)

## Install

  * [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
  * [Vagrant](http://www.vagrantup.com/downloads)
    * vagrant plugin install vagrant-berkshelf
    * vagrant plugin install vagrant-omnibus
  * [Chef-dk](http://downloads.getchef.com/chef-dk)
    * OSX
      * brew install caskroom/cask/brew-cask
      * brew cask install chefdk

### Note

Before run vagrant up --provision

export PATH=/opt/chefdk/bin:$PATH

Because RVM mess up PATH >:(

Source: https://github.com/berkshelf/vagrant-berkshelf/issues/212


If you get:

```bash
ERROR: You must specify at least one cookbook repo path
```

Run:

```bash
vagrant reload
```

Source: https://github.com/berkshelf/vagrant-berkshelf/issues/78


## Included Receipes

  * [Nginx](https://supermarket.getchef.com/cookbooks/nginx)
  * [php-fpm](https://supermarket.getchef.com/cookbooks/php-fpm)
  * [RVM](https://supermarket.getchef.com/cookbooks/rvm)

## Inspiration

  * [Vagrant + Ubuntu 14.04 + Chef Solo](http://www.akitaonrails.com/2014/07/28/small-bites-vagrant-ubuntu-14-04-chef-solo)
  * [Starting the Server Build](https://www.goettner.net/2013/starting-the-server-build/)
  * [Reginaldo Sousa: Estudando Vagrant + Chef](https://github.com/reginaldosousa/vagrant_chef)

## License and Authors

Author:: Antonio Carlos de Souza (ac.desouza@gmail.com)

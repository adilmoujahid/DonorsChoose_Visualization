# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  # upgrade from puphpet/debian75-x64 to debian/jessie64
  config.vm.box = "debian/jessie64"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # config.vm.network "public_network", ip: "192.168.2.17"
  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  config.vm.network "forwarded_port", guest: 27017, host: 27017

  # Set the base box requirements
  config.vm.provision "shell" do |s|
  s.inline = <<-SHELL

  # Install MongoDB - https://docs.mongodb.com/manual/tutorial/install-mongodb-enterprise-on-debian/

  # Import the MongoDB public GPG Key    
  apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6

  # Create the list file
  echo "deb http://repo.mongodb.com/apt/debian jessie/mongodb-enterprise/3.4 main" | tee /etc/apt/sources.list.d/mongodb-enterprise.list

  # Reload local package database
  apt-get update

  # Install the latest stable version of MongoDB Enterprise.
  apt-get install -y mongodb-enterprise

  # Set bind ips on config files - https://docs.mongodb.com/manual/reference/configuration-options/ 
  sed -i 's/bindIp = 127.0.0.1/bindIp = 0.0.0.0/' /etc/mongod.conf     

  # Restart MongoDB
  service mongod restart

  SHELL
end

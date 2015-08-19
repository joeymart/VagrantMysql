# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Every Vagrant virtual environment requires a box to build off of.
	config.vm.box = "precise64"
  # where to download the VM box if not already local (in ~/.vagrant.d/boxes)
  config.vm.box_url = "http://files.vagrantup.com/precise64.box" 
  
  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:4444" will access port 3306 on the guest machine.
 	config.vm.network "forwarded_port", guest: 3306, host: 4444

  # Create a private network, which allows host-only access to the machine using a specific IP.
 	config.vm.network "private_network", ip: "44.44.44.44"

  # a shell script to run when provisioning the vm (to setup our VM)
  config.vm.provision :shell, :path => "install-mysql.sh"

  # mount the current host machines dir in the new virtual machine as /vagrant (for easy file sharing)
  config.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777", "fmode=666"]

end

# -*- mode: ruby -*-
# vi: set ft=ruby :

file_to_disk = './tmp/large_disk.vdi'
#file2_to_disk = './tmp/large_disk2.vdi'

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise64"

  config.vm.provider "virtualbox" do |v|
    v.customize ['createhd', '--filename', file_to_disk, '--size', 10 * 1024]
    #v.customize ['createhd', '--filename', file2_to_disk, '--size', 10 * 1024]
    v.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 0, '--device', 0, '--type', 'hdd', '--medium', file_to_disk]
    #v.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', file2_to_disk]
  end

end

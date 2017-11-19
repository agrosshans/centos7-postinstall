# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.


Vagrant.configure(2) do |config|

  config.vm.define "centos7-1" do |centos71|
    centos71.vm.box = "centos/7"
    centos71.vm.hostname = "centos7-1"
    centos71.vm.network :forwarded_port, guest: 22, host: 2227, id: "ssh", disabled: true
    centos71.vm.network :forwarded_port, guest: 22, host: 2527, auto_correct: true
    centos71.vm.network "private_network", bridge: "vboxnet12", ip: "192.168.36.156", mac: "0800273E0E4A"
    centos71.vm.network "private_network", bridge: "vboxnet13", ip: "10.16.143.156", virtualbox__intnet: true, mac: "080027846870"
    centos71.vm.synced_folder "/Users/grosshaa/Ansible/myplaybooks/", "/vagrant", type: "virtualbox"
    centos71.vm.provider "virtualbox" do |vb|
    unless File.exist?('./centos7-1_VirtualDisk1.vmdk')
      vb.customize ['createhd', '--filename', './centos7-1_VirtualDisk1.vmdk', '--variant', 'Fixed', '--size', 1 * 1024]
      end
      vb.customize ['storageattach', :id,  '--storagectl', 'IDE', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', './centos7-1_VirtualDisk1.vmdk']
      end
    end

  config.vm.define "centos7-2" do |centos72|
    centos72.vm.box = "centos/7"
    centos72.vm.hostname = "centos7-2"
    centos72.vm.network :forwarded_port, guest: 22, host: 2228, id: "ssh", disabled: true
    centos72.vm.network :forwarded_port, guest: 22, host: 2528, auto_correct: true
    centos72.vm.network "private_network", bridge: "vboxnet12", ip: "192.168.36.157", mac: "0800279628FA"
    centos72.vm.network "private_network", bridge: "vboxnet13", ip: "10.16.143.157", virtualbox__intnet: true, mac: "08002744A461"
    centos72.vm.synced_folder "/Users/grosshaa/Ansible/myplaybooks/", "/vagrant", type: "virtualbox"
    centos72.vm.provider "virtualbox" do |vb|
    unless File.exist?('./centos7-2_VirtualDisk1.vmdk')
      vb.customize ['createhd', '--filename', './centos7-2_VirtualDisk1.vmdk', '--variant', 'Fixed', '--size', 1 * 1024]
      end
      vb.customize ['storageattach', :id,  '--storagectl', 'IDE', '--port', 1, '--device', 0, '--type', 'hdd', '--medium', './centos7-2_VirtualDisk1.vmdk']
      end
    end

end

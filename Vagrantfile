# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

hosts = {
  "host00" => "192.168.33.10",
  "host01" => "192.168.33.11",
  "host02" => "192.168.33.12"
}


Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    
  hosts.each do |name, ip|
      config.vm.define name do |machine|
        machine.vm.box = "precise32"
        machine.vm.hostname = "%s.example.org" % name
        machine.vm.network :private_network, ip: ip
        machine.vm.provider "virtualbox" do |v|
            v.name = name
            v.customize ["modifyvm", :id, "--memory", 200]
        end
      end
    end
end
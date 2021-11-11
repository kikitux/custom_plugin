# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.hostname = "golang"
  
  config.vm.provision "shell", path: "https://raw.githubusercontent.com/automodule/bash/main/install_terraform_11.sh"
  config.vm.provision "shell", path: "https://raw.githubusercontent.com/automodule/bash/main/install_golang-go-1.10.sh"
  config.vm.provision "shell", path: "https://raw.githubusercontent.com/automodule/bash/main/install_gcc.sh"
 
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024*2
    v.cpus = 2
  end

end

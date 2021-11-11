# Using a custom plugin

This repository describes the build and use of a custom plugin.  

In this example will build and use the custom plugin from [this Github project](https://github.com/petems/terraform-provider-extip). With this custom plugin we are able to get our external ip address with terraform. 


# Prerequisites

Vagrant [See documentation](https://www.vagrantup.com/docs/installation)  
Virtualbox [See documentation](https://www.virtualbox.org/wiki/Downloads)



# How to

There are 2 different chapters.  

- How to use the plugin.   
Follow these steps to use the custom plugin added to this repository
- How to build and use the plugin.   
Follow these steps to see the build of the custom plugin and use it  


## How to use the plugin
1. Clone the repository to your local machine
```
git clone https://github.com/munnep/custom_plugin.git
```
2. Change your directory
```
cd custom_plugin
```
3. Start a virtual machine with Vagrant
```
vagrant up
```
4. ssh into the virtual machine with Vagrant.
```
vagrant ssh
```
10. go to the directory ```/vagrant```
```
cd /vagrant
```
11. Terraform init
```
terraform init
```
12. Terraform apply
``` 
terraform apply
```
13. You should see the output of your external ip adres
```
data.extip.external_ip: Refreshing state...

Apply complete! Resources: 0 added, 0 changed, 0 destroyed.

Outputs:

external_ip = 88.1.2.13
```
14. exit out of the vagrant machine
```
exit
```
15. Stop the vagrant machine
```
vagrant halt
```
16. When you are completely done you can remove it
```
vagrant destroy
```



## How to build and use the plugin
1. Clone the repository to your local machine
```
git clone https://github.com/munnep/custom_plugin.git
```
2. Change your directory
```
cd custom_plugin
```
3. Start a virtual machine with Vagrant
```
vagrant up
```
4. ssh into the virtual machine with Vagrant.
```
vagrant ssh
```
5. change the owner of the go directory under the ```/home/vagrant``` user to ```vagrant```
```
sudo chown -R vagrant:vagrant ~/go/
```
6. Download the github project for the external IP
```
go get github.com/petems/terraform-provider-extip
```
7. Go to the created directory
```
cd ~/go/src/github.com/petems/terraform-provider-extip
```
8. Make the build
```
make build
```
9. copy the custom provider to ```/vagrant/terraform.d/plugins/linux_amd64``` 
```
mkdir -p /vagrant/terraform.d/plugins/linux_amd64
cp ~/go/bin/terraform-provider-extip /vagrant/terraform.d/plugins/linux_amd64/
```
10. go to the directory ```/vagrant```
```
cd /vagrant
```
11. Terraform init
```
terraform init
```
12. Terraform apply
``` 
terraform apply
```
13. You should see the output of your external ip adres
```
data.extip.external_ip: Refreshing state...

Apply complete! Resources: 0 added, 0 changed, 0 destroyed.

Outputs:

external_ip = 88.1.2.13
```
14. exit out of the vagrant machine
```
exit
```
15. Stop the vagrant machine
```
vagrant halt
```
16. When you are completely done you can remove it
```
vagrant destroy
```
# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure ("2") do |config|
	config.vm.box = "centos/7"
	config.vm.hostname = "demo"
	config.vm.network :private_network, ip: "192.168.33.10"
	config.vm.synced_folder ".", "/home/vagrant/sync", disabled: true
	config.vm.provision "shell", inline: <<-SHELL
		yum -y install epel-release
		yum -y install nginx
		echo “hello, vagrant” > /usr/share/nginx/html/index.html
		systemctl start nginx
	SHELL
end


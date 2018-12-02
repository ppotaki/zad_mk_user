# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

	config.vm.define "app" do |app|
	  app.vm.hostname = "server-app-01"
	  app.vm.box = "centos/7"
	  app.vm.network "private_network", ip: "10.1.10.10"
	  app.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/user_keys"
      app.vm.provision "shell", inline: "cat ~/.ssh/user_keys >> ~/.ssh/authorized_keys", privileged: false
	  end
	        
	config.vm.define "db" do |db|
      db.vm.hostname = "server-db-01"
      db.vm.box = "centos/7"
      db.vm.network "private_network", ip: "10.1.20.10"
      db.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/user_keys"
      db.vm.provision "shell", inline: "cat ~/.ssh/user_keys >> ~/.ssh/authorized_keys", privileged: false
	  end
end

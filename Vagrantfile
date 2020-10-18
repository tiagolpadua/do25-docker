# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.network :forwarded_port, guest: 80, host: 4567
  config.vm.network :forwarded_port, guest: 3306, host: 3306
  config.vm.provision "docker"
  config.vm.provision "shell", inline: "sudo curl --silent -L \"https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)\" -o /usr/local/bin/docker-compose"
  config.vm.provision "shell", inline: "sudo chmod +x /usr/local/bin/docker-compose"
end

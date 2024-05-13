# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.box_check_update = false
  config.vm.hostname = "nginx"
  config.vm.network "public_network", ip: "192.168.0.176"
 
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = "1"
   end



   config.vm.provision "shell", inline: <<-SHELL
    echo "insert your public key" >> ~vagrant/.ssh/authorized_keys
    mkdir -p ~root/.ssh
    cp ~vagrant/.ssh/auth* ~root/.ssh
    sudo sed -i 's/\PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
    systemctl restart sshd
   SHELL
end
# -*- mode: ruby -*-
# vi: set ft=ruby :
#https://gist.github.com/louisdorard/6095624
#https://thucnc.medium.com/how-to-forward-multiple-ports-from-vagrant-vm-to-host-machine-959d25923056

ENV['VAGRANT_NO_PARALLEL'] = 'yes'

$COMMANDS = <<-'BLOCK'
apt-get update
apt-get install vim git snap sshpass ansible dos2unix -y
chmod a+x /tmp/*.sh
find /tmp -type f |xargs dos2unix
BLOCK
        

Vagrant.configure(2) do |config|

  NodeCount = 1

  (1..NodeCount).each do |i|
    config.vm.define "ansible-server" do |node|
      node.vm.box = "bento/ubuntu-22.04"
      node.vm.hostname = "ansible.example.com"
      node.vm.network :forwarded_port, guest: 80,host: 80
      node.vm.network :forwarded_port, guest: 8080,host: 8080
      node.vm.provision "file", source: "main.sh", destination: "/tmp/main.sh"
      node.vm.provision "file", source: "config.sh", destination: "/tmp/config.sh"
      node.vm.provision "shell",privileged: true, inline: $COMMANDS
      node.vm.provision :shell, privileged: true, :inline => "bash /tmp/main.sh"
      node.vm.network "private_network", ip: "10.10.100.11#{i}"
      node.vm.provider "virtualbox" do |v|
        v.name = "ansible-server"
        v.memory = 6144
        v.cpus = 2
      end
    end
  end

end

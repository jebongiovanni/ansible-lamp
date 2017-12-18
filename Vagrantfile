# -*- mode: ruby -*-
# vi: set ft=ruby :
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'

Vagrant.configure("2") do |config|
  config.vm.define "control" do |subconfig|
    subconfig.vm.box = "geerlingguy/centos7"
    subconfig.vm.network "private_network", ip: "192.168.44.10"
#    subconfig.ssh.username = "vagrant"
    config.vm.hostname = "control"
    subconfig.ssh.insert_key = false
#    subconfig.ssh.private_key_path = ["keys/.ssh/vagrant_rsa", "~/.vagrant.d/insecure_private_key"]
#    subconfig.vm.provision "file", source: "keys/.ssh/vagrant_rsa.pub", destination: "~/.ssh/authorized_keys"
    subconfig.ssh.forward_agent = true
#    subconfig.vm.provision "shell", inline: <<-EOC
#    sudo sed -i -e "\\#PasswordAuthentication yes# s#PasswordAuthentication yes#PasswordAuthentication no#g", # /etc/ssh/sshd_config
#    sudo service sshd restart
#  EOC
    subconfig.vm.provision "shell", inline: <<-EOC
    sudo echo "192.168.44.10 control" | sudo tee -a /etc/hosts
    sudo service network restart
  EOC
end

  config.vm.define "lb01" do |subconfig|
    subconfig.vm.box = "geerlingguy/centos7"
##    subconfig.vm.network "forwarded_port", guest: 2200, host: 80
    subconfig.vm.network "private_network", ip: "192.168.44.20"
#    subconfig.ssh.username = "vagrant"
    config.vm.hostname = "lb01"
    subconfig.ssh.insert_key = false
#    subconfig.ssh.private_key_path = ["keys/.ssh/vagrant_rsa", "~/.vagrant.d/insecure_private_key"]
#    subconfig.vm.provision "file", source: "keys/.ssh/vagrant_rsa.pub", destination: "~/.ssh/authorized_keys"
    subconfig.ssh.forward_agent = true
#    subconfig.vm.provision "shell", inline: <<-EOC
#    sudo sed -i -e "\\#PasswordAuthentication yes# s#PasswordAuthentication yes#PasswordAuthentication no#g" /etc/ssh/sshd_config
#    sudo service sshd restart
#  EOC
    subconfig.vm.provision "shell", inline: <<-EOC
    sudo echo "192.168.44.20 lb01" | sudo tee -a /etc/hosts
    sudo service network restart
  EOC
end

  config.vm.define "appsrv01" do |subconfig|
    subconfig.vm.box = "geerlingguy/centos7"
#    subconfig.vm.network "forwarded_port", guest: 8081, host: 80
    subconfig.vm.network "private_network", ip: "192.168.44.30"
#    subconfig.ssh.username = "vagrant"
    config.vm.hostname = "appsrv01"
    subconfig.ssh.insert_key = false
#    subconfig.ssh.private_key_path = ["keys/.ssh/vagrant_rsa", "~/.vagrant.d/insecure_private_key"]
#    subconfig.vm.provision "file", source: "keys/.ssh/vagrant_rsa.pub", destination: "~/.ssh/authorized_keys"
    subconfig.ssh.forward_agent = true
#    subconfig.vm.provision "shell", inline: <<-EOC
#    sudo sed -i -e "\\#PasswordAuthentication yes# s#PasswordAuthentication yes#PasswordAuthentication no#g" /etc/ssh/sshd_config
#    sudo service sshd restart
#  EOC
    subconfig.vm.provision "shell", inline: <<-EOC
    sudo echo "192.168.44.30 appsrv01" | sudo tee -a /etc/hosts
    sudo service network restart
  EOC
  end

  config.vm.define "appsrv02" do |subconfig|
    subconfig.vm.box = "geerlingguy/centos7"
#   subconfig.vm.network "forwarded_port", guest: 8082, host: 80
    subconfig.vm.network "private_network", ip: "192.168.44.40"
#    subconfig.ssh.username = "vagrant"
    config.vm.hostname = "appsrv02"
    subconfig.ssh.insert_key = false
#    subconfig.ssh.private_key_path = ["keys/.ssh/vagrant_rsa", "~/.vagrant.d/insecure_private_key"]
#    subconfig.vm.provision "file", source: "keys/.ssh/vagrant_rsa.pub", destination: "~/.ssh/authorized_keys"
    subconfig.ssh.forward_agent = true
#    subconfig.vm.provision "shell", inline: <<-EOC
#    sudo sed -i -e "\\#PasswordAuthentication yes# s#PasswordAuthentication yes#PasswordAuthentication no#g" /etc/ssh/sshd_config
#    sudo service sshd restart
#  EOC
    subconfig.vm.provision "shell", inline: <<-EOC
    sudo echo "192.168.44.40 appsrv02" | sudo tee -a /etc/hosts
    sudo service network restart
  EOC
  end

  config.vm.define "dbsrv01" do |subconfig|
    subconfig.vm.box = "geerlingguy/centos7"
#    subconfig.vm.network "forwarded_port", guest: 3306, host: 3306
    subconfig.vm.network "private_network", ip: "192.168.44.50"
#    subconfig.ssh.username = "vagrant"
    config.vm.hostname = "dbsrv01"
    subconfig.ssh.insert_key = false
#    subconfig.ssh.private_key_path = ["keys/.ssh/vagrant_rsa", "~/.vagrant.d/insecure_private_key"]
#    subconfig.vm.provision "file", source: "keys/.ssh/vagrant_rsa.pub", destination: "~/.ssh/authorized_keys"
    subconfig.ssh.forward_agent = true
#    subconfig.vm.provision "shell", inline: <<-EOC
#    sudo sed -i -e "\\#PasswordAuthentication yes# s#PasswordAuthentication yes#PasswordAuthentication no#g" /etc/ssh/sshd_config
#    sudo service sshd restart
#  EOC
    subconfig.vm.provision "shell", inline: <<-EOC
    sudo echo "192.168.44.50 dbsrv01" | sudo tee -a /etc/hosts
    sudo service network restart
  EOC
  end
end

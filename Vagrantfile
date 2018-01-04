# -*- mode: ruby -*-

Vagrant.configure("2") do |config|

  # Ubuntu
  ########

  # Ubuntu 16.04
  config.vm.define "ubuntu1604-chrony" do |node|
    node.vm.box = "ubuntu/xenial64"
    node.vm.hostname = "ubuntu1604-chrony"
		node.vm.provider "virtualbox" do |v|
		  v.linked_clone = true
		end
    node.vm.provision "shell",
      inline: "sudo sed -i 's/archive.ubuntu.com/free.nchc.org.tw/g' /etc/apt/sources.list"
    node.vm.provision "shell",
      inline: "sudo apt-get update && sudo apt-get install -y python"
    node.vm.provision "ansible" do |ansible|
      ansible.playbook = "provision.yml"
      ansible.become = true
    end
  end

  # Debian
  ########

  # Debian 9
  config.vm.define "debian9-chrony" do |node|
    node.vm.box = "debian/stretch64"
    node.vm.hostname = "debian9-chrony"
		node.vm.provider "virtualbox" do |v|
		  v.linked_clone = true
		end
    node.vm.provision "ansible" do |ansible|
      ansible.playbook = "provision.yml"
      ansible.become = true
    end
  end

  # CentOS (EL)
  #############

  # CentOS 7
  config.vm.define "centos7-chrony" do |node|
    node.vm.box = "bento/centos-7.4"
    node.vm.hostname = "centos7-chrony"
		node.vm.provider "virtualbox" do |v|
		  v.linked_clone = true
		end
    node.vm.provision "ansible" do |ansible|
      ansible.playbook = "provision.yml"
      ansible.become = true
    end
  end

end

# vi: set ft=ruby :

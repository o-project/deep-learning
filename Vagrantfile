# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "centos/7"

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.network "private_network", ip: "192.168.33.88"

  config.vm.synced_folder ".", "/deep-learning"

  config.vm.provision "ansible_local", run: "always" do |ansible|
      ansible.playbook = "./ansible/playbook/main.yml"
      ansible.inventory_path = "./ansible/hosts/hosts.yml"
      ansible.limit = "all"
  end

end

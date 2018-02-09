# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX = "bento/centos-7.4"

Machine = Struct.new(:name, :ipv4)

MACHINES = [
  Machine.new("web", "10.0.0.10"),
  Machine.new("worker", "10.0.0.20"),
]

Vagrant.configure("2") do |config|
  MACHINES.each do |machine|
    name = machine[:name]
    config.vm.define name do |subconfig|
      subconfig.vm.box = BOX
      subconfig.vm.hostname = name + ".qq"
      subconfig.vm.network :private_network, ip: machine[:ipv4]
      subconfig.vm.provision :ansible_local do |ansible|
        ansible.compatibility_mode = "2.0"
        ansible.become = true
        ansible.playbook = "playbook.yml"
      end
    end
  end
end

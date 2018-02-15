# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX = "bento/centos-7.4"

Vagrant.configure("2") do |config|
    config.vm.box = BOX
    config.vm.provision :ansible_local do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.become = true
      ansible.playbook = "playbook.yml"
    end
  end
end

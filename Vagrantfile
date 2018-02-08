# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX = "bento/centos-7.4"

Vagrant.configure("2") do |config|
  [:web, :worker].each do |name|
    config.vm.define name do |subconfig|
      subconfig.vm.box = BOX
    end
  end
end

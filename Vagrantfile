# -*- mode: ruby -*-
# vi: set ft=ruby :

BOXES = {
  master: {
    debian: ['bento/debian-12', { nodes: 1, ram: 1024, cpu: 1 }],
    rocky: ['bento/rockylinux-9', { nodes: 1, ram: 1024, cpu: 1 }],
  },
  slave: {
    debian: ['bento/debian-12', { nodes: 2, ram: 512, cpu: 1 }],
    rocky: ['bento/rockylinux-9', { nodes: 2, ram: 512, cpu: 1 }],
  },
}

Vagrant.configure("2") do |config|
  
  # Disabling default shared folder for all vm
  config.vm.synced_folder ".", "/vagrant", disabled: true

  ip_count = 0

  BOXES.each do |role, type|
    type.each do |name, (box, options)|
      options[:nodes].times do |i|
        config.vm.define "#{role}-#{name}-#{i + 1}" do |machine|

          machine.vm.box = "#{box}"
          machine.vm.hostname = "#{role}-#{name}-#{i + 1}"
          machine.vm.network "private_network", ip: "192.168.56.1#{ip_count}"
          ip_count += 1

          machine.vm.provider "virtualbox" do |vb|
            vb.name = "#{role}-#{name}-#{i + 1}"
            vb.memory = options[:ram]
            vb.cpus = options[:cpu]
          end
        end
      end
    end
  end
end

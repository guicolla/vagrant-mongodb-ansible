# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  # config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.network "public_network"
  # config.vm.synced_folder "../data", "/vagrant_data"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "512"
  end


  (2..5).each do |i|
    config.vm.define "node#{i}" do |node|
      node.vm.hostname = "node#{i}"
      node.vm.network "private_network",ip: "192.168.200.#{i}"
    end
  end
  
 config.vm.provision "shell", inline: <<-SHELL
    echo "provisionou"
    echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDafbJICiEOYrLtxlWsnvRy5IgfW1YELKXN6f5tuKbBDjdyMRLZFI4uqpja45zYyfGV1xCzTokfw9I42fGTj0PC/NZ1Fb2PdL7uyFd/rUcpiUj/du61jKckRrpXL7+oaGl7DLPgepaN0RhyKHCj53xa1i6mAgvyi1oWj5v2XLxz+NlI1+C+DGFPK6RqHhAcVjn9X+IRZ07BtpwLxBC7K5C6MI9cO66qZSgCa8XD+K8FCWqYKLuwlPNCGqaCD0vGo8JmJef4ShSp4L4fVCySR5LXfRNK86Fvcel59CB+TpY/CXqqf2/V71LFumQTdTtktCKeFrqTu8w+MuRR7p9VCIPd root@colla" >> /home/vagrant/.ssh/authorized_keys
  SHELL

end

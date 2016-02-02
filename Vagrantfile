# -*- mode: ruby -*-
Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.provider "virtualbox" do |v|
    v.name   = "ansible-baseline"
    v.memory = 1024
  end

  config.vm.provision "shell",
    inline: "apt-get update && apt-get -y upgrade"

  config.vm.provision "shell",
    :path => "tests/specs.sh",
    :upload_path => "/home/vagrant/specs",
    # change role name below
    :args => "--install ansible-baseline"
end

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.box = "ubuntu/trusty32"
  config.vm.provision :file, source: "versions.sh", destination: "/tmp/railsbridge-versions.sh"
  config.vm.provision :shell, path: "provision-root-install.sh"
  config.vm.provision :shell, path: "https://toolbelt.heroku.com/install-ubuntu.sh"
  config.vm.provision :shell, path: "provision-user-install.sh", privileged: false
  config.vm.provision :shell, path: "provision-root-cleanup.sh"
  config.vm.network :forwarded_port, guest: 3000, host: 3000
end

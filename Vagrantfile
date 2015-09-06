# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version.
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "ubuntu/vivid64"

  # forward the ssh agent to the guest machine
  config.ssh.forward_agent = true

  # Xwindows forwarding
  config.ssh.forward_x11 = true

  # use shell provisioner to install ansible
  config.vm.provision "shell",
    inline: "apt-get install -y ansible"

  # run the ansible playbook
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/playbook.yaml"
  end

end

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.box_check_update = true
  config.vm.synced_folder ".", "vagrant", disabled: true

  config.vm.provider "virtualbox" do |vb|
#    vb.gui = true
    vb.cpus = 2
    vb.memory = "4096"
    vb.customize ["modifyvm", :id, "--usb", "on"]
    
    #No need for USB 2 + Extension Pack
    #vb.customize ["modifyvm", :id, "--usbehci", "on"]

    vb.customize ["usbfilter", "add", "0",
        "--target", :id,
        "--name", "Ledger",
        "--manufacturer", "Ledger"]
  end

  config.vm.provision "ansible" do |ansible|
    # ansible.verbose = true
    ansible.playbook = "provisioning/main.yml"
    ansible.config_file = "provisioning/ansible.cfg"
    ansible.galaxy_role_file = "provisioning/requirements.yml"
  end

end

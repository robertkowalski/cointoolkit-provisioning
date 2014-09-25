# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.define "machine", primary: true do |machine|
      machine.vm.provision "ansible" do |ansible|
      ansible.playbook = "main.yml"
      ansible.extra_vars = {
        ansible_ssh_user: "vagrant",
        couchdb_admin_password: "admin"
      }
      ansible.verbose = "vv"
      ansible.groups = {
        "vagrantgroup" => ["machine"]
      }
    end
  end
end

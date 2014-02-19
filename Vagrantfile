VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64"
  config.vm.network :private_network, ip: "192.168.50.35"

  config.vm.synced_folder ".", "/vagrant", type: "nfs"
  config.vm.hostname = 'site.local'

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/vagrant.yml"
    ansible.inventory_path = "provisioning/vagrant"
    ansible.verbose = "vvvv"
  end
end

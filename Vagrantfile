VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network :private_network, ip: "192.168.123.21"
  config.vm.hostname = "chat"

  config.vm.provider :virtualbox do |v|
    v.name = "chat"
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.define :chat do |chat|
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/bootstrap.yml"
  end
end

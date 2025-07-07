Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

  config.vm.define "db" do |db_config|
    db_config.vm.network "private_network", ip: "192.168.56.10"
    db_config.vm.provision "ansible" do |ansible|
      ansible.playbook = "provision.yml"
      ansible.inventory_path = "inventory/databases.yml"
    end
  end

end

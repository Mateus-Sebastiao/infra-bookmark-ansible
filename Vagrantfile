Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

  config.vm.define "db" do |db_config|
    db_config.vm.network "private_network", ip: "192.168.56.10"
    db_config.vm.provision "ansible" do |ansible|
      ansible.playbook = "provision.yml"
      ansible.inventory_path = "inventory/hosts.yml"
      ansible.limit = "databases"
    end
  end

  config.vm.define "web" do |web_config|
    web_config.vm.network "private_network", ip: "192.168.56.11"
    web_config.vm.provision "ansible" do |ansible|
      ansible.playbook = "provision.yml"
      ansible.inventory_path = "inventory/hosts.yml"
      ansible.limit = "webservers"
    end
  end

end

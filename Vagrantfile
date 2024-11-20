Vagrant.configure("2") do |config|
  # Utilisation de l'image Ubuntu 22.04 pour toutes les machines
  config.vm.box = "ubuntu/jammy64"

  # Manager (où Ansible sera installé)
  config.vm.define "manager" do |manager|
    manager.vm.hostname = "manager"
    manager.vm.network "private_network", type: "dhcp"
    manager.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 1
    end
    manager.vm.provision "shell", inline: <<-SHELL
      sudo apt update
      sudo apt install -y ansible
    SHELL
  end

  # Node 1
  config.vm.define "node1" do |node1|
    node1.vm.hostname = "node1"
    node1.vm.network "private_network", type: "dhcp"
    node1.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
  end

  # Node 2
  config.vm.define "node2" do |node2|
    node2.vm.hostname = "node2"
    node2.vm.network "private_network", type: "dhcp"
    node2.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
  end
end

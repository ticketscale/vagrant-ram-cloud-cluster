# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|

 config.vm.box = "ubuntu/trusty64"
 config.vm.network "private_network", type: "dhcp"

 config.vm.define "zookeeper1" do |zookeeper1|
    zookeeper1.vm.provision "ansible" do |ansible|
      ansible.playbook = "zookeeper.yml"
      ansible.sudo = true
    end
    zookeeper1.vm.hostname = "zookeeper1.dev"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 1
    end
    zookeeper1.vm.network :private_network, :ip => '10.20.0.2'
    zookeeper1.vm.provision :hosts, :sync_hosts => true
  end

  config.vm.define "zookeeper2" do |zookeeper2|
    zookeeper2.vm.provision "ansible" do |ansible|
      ansible.playbook = "zookeeper.yml"
      ansible.sudo = true
    end
    zookeeper2.vm.hostname = "zookeeper2.dev"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 1
    end
    zookeeper2.vm.network :private_network, :ip => '10.20.0.3'
    zookeeper2.vm.provision :hosts, :sync_hosts => true
  end

  config.vm.define "zookeeper3" do |zookeeper3|
    zookeeper3.vm.provision "ansible" do |ansible|
      ansible.playbook = "zookeeper.yml"
      ansible.sudo = true
    end
    zookeeper3.vm.hostname = "zookeeper3.dev"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 1
    end
    zookeeper3.vm.network :private_network, :ip => '10.20.0.4'
    zookeeper3.vm.provision :hosts, :sync_hosts => true
  end


  config.vm.define "storageserver1" do |storageserver1|
    storageserver1.vm.provision "ansible" do |ansible|
      ansible.playbook = "server.yml"
      ansible.sudo = true
    end
    storageserver1.vm.hostname = "storageserver1.dev"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = "4096"
        vb.cpus = 8
    end
    storageserver1.vm.network :private_network, :ip => '10.20.0.5'
    storageserver1.vm.provision :hosts, :sync_hosts => true
  end

  config.vm.define "storageserver2" do |storageserver2|
    storageserver2.vm.provision "ansible" do |ansible|
      ansible.playbook = "server.yml"
      ansible.sudo = true
    end
    storageserver2.vm.hostname = "storageserver2.dev"
    config.vm.provider "virtualbox" do |vb|
        vb.memory = "4096"
        vb.cpus = 8
    end
    storageserver2.vm.network :private_network, :ip => '10.20.0.6'
    storageserver2.vm.provision :hosts, :sync_hosts => true
  end

end
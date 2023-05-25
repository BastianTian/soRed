Vagrant.configure("2") do |config|
  if Vagrant.has_plugin? "vagrant-vbguest"
    config.vbguest.no_install = true
    config.vbguest.auto_update = false
    config.vbguest.no_remote = true
  end
  config.vm.define :web do |web|
    config.vm.box = "bento/centos-stream-9"
    config.vm.box_version = "202301.20.0"
    web.vm.provision "shell", path: "web.sh.txt"
    web.vm.network :private_network, ip: "192.168.50.4"
    web.vm.hostname = "web"
    web.vm.provider "virtualbox" do |v|
      v.cpus = 2  
    end
  end
  config.vm.define :firewall do |firewall|
    config.vm.box = "bento/centos-stream-9"
    config.vm.box_version = "202301.20.0"
    firewall.vm.provision "shell", path: "firewall.sh.txt"
    firewall.vm.network :private_network, ip: "192.168.50.5"
    firewall.vm.network :public_network, ip: "11.11.35.200"
    firewall.vm.hostname = "firewall"
    firewall.vm.provider "virtualbox" do |v|
      v.cpus = 2  
    end
  end
  config.vm.define :db do |db|
    config.vm.box = "bento/centos-stream-9"
    config.vm.box_version = "202301.20.0"
    db.vm.provision "shell", path: "db.sh.txt"
    db.vm.network :private_network, ip: "192.168.50.7"
    db.vm.hostname = "db"
    db.vm.provider "virtualbox" do |v|
      v.cpus = 2  
    end
  end
  config.vm.define :bl do |bl|
    config.vm.box = "bento/centos-stream-9"
    config.vm.box_version = "202301.20.0"
    bl.vm.provision "shell", path: "bl.sh.txt"
    bl.vm.network :private_network, ip: "192.168.50.8"
    bl.vm.hostname = "bl"
    bl.vm.provider "virtualbox" do |v|
      v.cpus = 2  
    end
  end
end
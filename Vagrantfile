Vagrant.configure("2") do |config|
  config.vm.boot_timeout = 600
  config.vm.provision "shell", inline: <<-SHELL
    echo "192.168.99.100 controlplane" >> /etc/hosts
    echo "192.168.99.101 worker" >> /etc/hosts
  SHELL
  config.vm.box = "ubuntu/focal64"
  config.vm.define "controlplane" do |controlplane|

    controlplane.ssh.insert_key = false
    controlplane.vm.box = "ubuntu/focal64"
    controlplane.vm.hostname = "controlplane"
    controlplane.vm.network "private_network", ip:"192.168.99.100", :adapter => 2
    controlplane.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = "2"
    end
  end

  config.vm.define "worker" do |worker|
    worker.ssh.insert_key = false
    worker.vm.hostname = "worker"
    worker.vm.network "private_network", ip:"192.168.99.101", :adapter => 2
    worker.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = "2"
    end
  end

end
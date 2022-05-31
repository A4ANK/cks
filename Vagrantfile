Vagrant.configure("2") do |config|

  config.vm.provision "shell", inline: <<-SHELL
    echo "192.168.99.100 master" >> /etc/hosts
    echo "192.168.99.101 worker" >> /etc/hosts
  SHELL
  config.vm.box = "ubuntu/focal64"
  config.vm.define "master" do |master|

    master.ssh.insert_key = false
    master.vm.box = "ubuntu/focal64"
    master.vm.hostname = "master"
    master.vm.network "private_network", ip:"192.168.99.100", :adapter => 2
    master.vm.provider "virtualbox" do |vb|
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
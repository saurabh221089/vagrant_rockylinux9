Vagrant.configure("2") do |config|
	config.vm.box = "rockylinux/9"
	config.vm.network "private_network", ip: "192.168.56.100"
	config.vm.provider "virtualbox" do |vb|
		vb.name = "rockylinux9"
    vb.memory = "2048"
    vb.cpus = "2"
	end
	config.vm.boot_timeout=600
	config.vm.provision "shell", inline: <<-SHELL
		sudo dnf -y upgrade
		echo "##### Creating saurabh user #####"
		sudo useradd saurabh
		sudo mkdir -p /home/saurabh/.ssh
		sudo touch /home/saurabh/.ssh/authorized_keys
		sudo chown saurabh:saurabh /home/saurabh/.ssh/authorized_keys
		sudo chmod 600 /home/saurabh/.ssh/authorized_keys
		echo "ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIBzEkJqpOH+212m1p6JKXl8Qz6LG/SsrNM25N22CemzW saura@DESKTOP-EJD8A2T" | sudo tee -a /home/saurabh/.ssh/authorized_keys
		sudo echo "saurabh ALL=(ALL:ALL) NOPASSWD:ALL" > /etc/sudoers.d/saurabh
		sudo chmod 440 /etc/sudoers.d/saurabh
	 SHELL
end
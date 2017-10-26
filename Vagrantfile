Vagrant.configure(2) do |config|

	config.vm.define "symfony" do |symfony|
		symfony.vm.box = "ubuntu/trusty64"
		symfony.vm.hostname = "symfony.dev"
		symfony.vm.network :private_network, ip: "192.168.33.151"

		symfony.vm.provision :ansible do |ansible|
			ansible.playbook = "provisioning/playbook.yml"
		end

		symfony.vm.provider "virtualbox" do |v|
			v.memory = 1024
			v.cpus = 2
			v.name = "Ubuntu LAMP"
		end
	end

       # config.vm.synced_folder ".", "/vagrant", type: "nfs"

	### Alex ###

	config.vm.define "centos" do |centos|
		centos.vm.box = "centos/7"
		centos.vm.hostname = "centos"

		#ssh config
		# centos.ssh.insert_key = false
		# centos.ssh.private_key_path = ["keys/private", "~/.vagrant.d/insecure_private_key"]
		# centos.vm.provision "file", source: "keys/public", destination: "~/.ssh/authorized_keys"

		centos.vm.network :private_network, ip: "192.168.33.152"

		config.vm.provision :ansible do |ansible|
			ansible.playbook = "provisioning/playbook.yml"
		end

		centos.vm.provider "virtualbox" do |v|
			v.memory = 1024
			v.cpus = 2
			v.name = "Centos LAMP"
		end
	end

end

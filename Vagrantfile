Vagrant.configure(2) do |config|

	config.vm.define "symfony" do |symfony|
		symfony.vm.box = "ubuntu/trusty64"
		symfony.vm.hostname = "symfony.dev"
		symfony.vm.network :private_network, ip: "192.168.33.151"

		symfony.vm.provision :ansible do |ansible|
			ansible.playbook = "provisioning/playbook.yml"
		end
	end

       # config.vm.synced_folder ".", "/vagrant", type: "nfs"

	config.vm.provider "virtualbox" do |v|
		v.memory = 1024
		v.cpus = 2
	end

	### Alex ###

	config.vm.define "config" do |config|
		config.vm.box = "centos/7"
		config.vm.hostname = "centOS.dev"
		config.vm.network :private_network, ip: "192.168.33.152"

		config.vm.provision :ansible do |ansible|
			ansible.playbook = "provisioning/playbook.yml"
		end
	end

       # config.vm.synced_folder ".", "/vagrant", type: "nfs"

	config.vm.provider "virtualbox" do |v|
		v.memory = 1024
		v.name = "Vagrant LAMP"
	end
end

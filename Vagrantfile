VAGRANTFILE_API_VERSION = "2"
Vagrant.configure("2") do |config|
	config.vm.box = "vagrant-centos"
	config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.1/centos65-x86_64-20131205.box"
	config.vm.provider "virtualbox" do |v| 
		v.customize [ "modifyvm", :id, "--cpus", "2" ]
		v.customize [ "modifyvm", :id, "--memory", "3584" ]
	end
	
	config.vm.define :bigtopcentos2 do |bigtopcentos2|
		bigtopcentos2.vm.box = config.vm.box
		bigtopcentos2.vm.box_url = config.vm.box_url
		bigtopcentos2.vm.network :private_network, ip: "10.10.10.22"
		bigtopcentos2.vm.hostname = "rs2"
		bigtopcentos2.vm.provision :shell, :path => "provision.sh"
	end
end

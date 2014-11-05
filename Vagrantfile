Vagrant.configure("2") do |config|
  config.vm.define "appmgr" do |machine|
    machine.vm.box = "ubuntu/trusty64"
    machine.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/trusty/20140507/trusty-server-cloudimg-amd64-vagrant-disk1.box"
    machine.vm.hostname = "appmgr"
    machine.vm.network :private_network, ip: "192.168.33.12"
    machine.vm.provider "virtualbox" do |v|
      v.name = "appmgr"
      v.customize ["modifyvm", :id, "--memory", 512]
    end
    machine.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/install.yml"
      ansible.verbose = "vv"
    end
  end
end

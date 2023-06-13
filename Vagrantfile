# My first Vagrant file
Vagrant.require_version ">= 1.8.0"

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--uart1", "0x3F8", "4"]
    v.customize ["modifyvm", :id, "--uartmode1", "file", File::NULL]
    v.memory = 2048
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.verbose = "v"
#    ansible.playbook = "/Users/ash/MainStream/vagrant/vagrant/playbook.yml"
    ansible.playbook = "vagrant/playbook.yml"
  end
end
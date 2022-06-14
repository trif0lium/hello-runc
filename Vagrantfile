Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.define 'ubuntu'
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--nested-hw-virt", "on"]
    v.memory = 10240
    v.cpus = 4
  end
  config.vm.insert_key = false
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "ansible-playbooks/firecracker-containerd.yml"
  end
end

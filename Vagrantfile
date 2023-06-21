Vagrant.configure("2") do |config|

  ###################################################################################
  config.vm.define "gitlab-ce" do |node|

    # which image to use
    node.vm.box = "generic/rocky9"

    # sizing of the VMs
    node.vm.provider "libvirt" do |lv|
      lv.random_hostname = false
      lv.memory = 8196
      lv.cpus = 2
    end

    # set the hostname
    node.vm.hostname = "gitlab-ce"

    # disable shared folders
    node.vm.synced_folder ".", "/vagrant", disabled: true
    node.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = '2.0'
      ansible.playbook = "ansible/playbook-all_nodes.yml"
    end # node.vm.provision

  end # config.vm.define

end # Vagrant.configure

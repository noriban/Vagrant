Vagrant.configure("2") do |config|
    config.vm.box = "bento/ubuntu-20.04"
   
    config.vm.provider "virtualbox" do |v|
      v.memory = 10240
      v.cpus = 3
    end

    config.vm.network "private_network", ip: "192.168.44.44"

    config.vm.provision "ansible_local" do |ansible|
        ansible.galaxy_role_file = 'requirements.yml'
        ansible.galaxy_roles_path = "/etc/ansible/roles"
        ansible.galaxy_command = "sudo ansible-galaxy install --role-file=%{role_file} --roles-path=%{roles_path}"
        ansible.playbook = "playbooks/init.yml"
    end
    
  end
   
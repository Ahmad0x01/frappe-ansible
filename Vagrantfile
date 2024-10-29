Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-22.04"
  config.vm.box_version = "202407.23.0"
  config.vm.network "private_network", ip: "192.168.56.10"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

#   config.vm.provision "shell", inline: <<-SHELL
#   if ! id -u mashedbytes > /dev/null 2>&1; then
#     sudo useradd -m -s /bin/bash mashedbytes
#     sudo usermod -aG sudo mashedbytes
#   fi
#   sudo mkdir -p /home/mashedbytes/.ssh
#   sudo cp /home/vagrant/.ssh/authorized_keys /home/mashedbytes/.ssh/
#   sudo chown -R mashedbytes:mashedbytes /home/mashedbytes/.ssh
#   sudo chmod 700 /home/mashedbytes/.ssh
#   sudo chmod 600 /home/mashedbytes/.ssh/authorized_keys
# SHELL


  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbooks/site.yml"
    ansible.compatibility_mode = "2.0"
    # ansible.extra_vars = {
    #   ansible_user: "mashedbytes"
    # }
  end
end

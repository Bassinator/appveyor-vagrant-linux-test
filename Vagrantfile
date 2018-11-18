Vagrant.configure("2") do |config|

  config.vm.provider "virtualbox" do |vbox|
    vbox.customize ['modifyvm', :id, '--clipboard', 'bidirectional']
    vbox.customize ["modifyvm", :id, "--vram", "64"]
    vbox.memory = 2048
    vbox.cpus = 2
    vbox.gui = true
  end
  config.vm.box = "centos/7"
  config.vm.synced_folder ".", "/vagrant", disabled: true

  #config.vm.provision "file", source: "roles", destination: "/vagrant/roles/"
  config.vm.provision "file", source: "main.yml", destination: "/home/vagrant/main.yml"
  config.vm.provision "file", source: "requirements.yml", destination: "/home/vagrant/requirements.yml"
  
  config.vm.provision "shell", inline: "ansible-galaxy install --role-file='/home/vagrant/requirements.yml' --roles-path='/home/vagrant/roles' --force"

  config.vm.provision "shell", inline: "ansible-playbook --connection=local --inventory 127.0.0.1, /home/vagrant/main.yml"
  
end

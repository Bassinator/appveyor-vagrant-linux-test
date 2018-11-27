Vagrant.configure("2") do |config|

  # config.vm.box = "centos/7"
  config.vm.box = "jasonc/centos7-32bit"

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 1
    vb.customize ["modifyvm", :id, "--nictype1", "Am79C973"]
    vb.customize ['modifyvm', :id, '--cableconnected1', 'on']
    vb.customize ["modifyvm", :id, "--hwvirtex", "off"] 
  end

  # config.vm.synced_folder ".", "/vagrant", disabled: true
  #
  # config.vm.provision "file", source: "main.yml", destination: "/home/vagrant/main.yml"
  # config.vm.provision "file", source: "requirements.yml", destination: "/home/vagrant/requirements.yml"
  #
  # config.vm.provision "shell", inline: "ansible-galaxy install --role-file='/home/vagrant/requirements.yml' --roles-path='/home/vagrant/roles' --force"
  #
  # config.vm.provision "shell", inline: "ansible-playbook --connection=local --inventory 127.0.0.1, /home/vagrant/main.yml"

end

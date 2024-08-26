Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true

  # DB_VM
  config.vm.define "db01" do |db01|
    db01.vm.box = "eurolinux-vagrant/centos-stream-9"
    db01.vm.hostname = "db01"
    db01.vm.network "private_network", ip: "192.168.56.15"
    db01.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
    end

    # Install EPEL release and Ansible
    db01.vm.provision "shell", inline: <<-SHELL
      sudo dnf install -y epel-release
      sudo dnf install -y ansible
    SHELL

    db01.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "mariadb.yml"
    end
  end

  # Memcache VM 
  config.vm.define "mc01" do |mc01|
    mc01.vm.box = "eurolinux-vagrant/centos-stream-9"
    mc01.vm.hostname = "mc01"
    mc01.vm.network "private_network", ip: "192.168.56.14"
    mc01.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end

    # Install EPEL release and Ansible
    mc01.vm.provision "shell", inline: <<-SHELL
      sudo dnf install -y epel-release
      sudo dnf install -y ansible
    SHELL

    mc01.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "Memcashe.yml"
    end
  end

  # RabbitMQ VM
  config.vm.define "rmq01" do |rmq01|
    rmq01.vm.box = "eurolinux-vagrant/centos-stream-9"
    rmq01.vm.hostname = "rmq01"
    rmq01.vm.network "private_network", ip: "192.168.56.13"
    rmq01.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end

    # Install EPEL release and Ansible
    rmq01.vm.provision "shell", inline: <<-SHELL
      sudo dnf install -y epel-release
      sudo dnf install -y ansible
    SHELL

    rmq01.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "rmq.yml"
    end
  end

  # Tomcat VM
config.vm.define "app01" do |app01|
  app01.vm.box = "eurolinux-vagrant/centos-stream-9"
  app01.vm.hostname = "app01"
  app01.vm.network "private_network", ip: "192.168.56.12"
  app01.vm.provider "virtualbox" do |vb|
    vb.memory = "4200"
  end

  # Install Python3, pip, and Ansible using pip with retries
  app01.vm.provision "shell", inline: <<-SHELL
    # Ensure the system is updated and required dependencies are installed
    sudo dnf makecache --refresh
    sudo dnf install -y python3 python3-pip

    # Upgrade pip and install Ansible with retries
    for i in {1..5}; do
      sudo pip3 install --upgrade pip && break || sleep 15
    done

    for i in {1..5}; do
      sudo pip3 install ansible && break || sleep 15
    done

    # Install Ansible Galaxy collection with retries
    for i in {1..5}; do
      ansible-galaxy collection install community.general && break || sleep 15
    done
  SHELL

  # Provisioning with ansible_local
  app01.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "app01.yml"
    ansible.compatibility_mode = "2.0" # Ensures compatibility with Ansible collections
  end
end


  # Nginx VM
  config.vm.define "web01" do |web01|
    web01.vm.box = "ubuntu/jammy64"
    web01.vm.hostname = "web01"
    web01.vm.network "private_network", ip: "192.168.56.11"
    web01.vm.provider "virtualbox" do |vb|
      vb.gui = true
      vb.memory = "1024"
    end

    # Update package list and install Ansible
    web01.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y ansible
    SHELL

    web01.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "web01.yml"
    end
  end

end

Vagrant.configure("2") do |config|
  config.vm.define "kali" do |kali|
    kali.vm.box = "kalilinux/rolling"

    # Create a forwarded port
    # kali.vm.network "forwarded_port", guest: 80, host: 8080

    # Create a private network. In VirtualBox, this is a Host-Only network
    # kali.vm.network "private_network", ip: "192.168.33.10"

    # VirtualBox specific settings
    kali.vm.provider "virtualbox" do |vb|
      # Hide the VirtualBox GUI when booting the machine
      vb.gui = false

      # Customize the VM:
      vb.memory = "4096"
      vb.cpus = 2
      vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
      vb.customize ["modifyvm", :id, "--draganddrop", "bidirectional"]
    end

    # Provision the machine with a shell script
    kali.vm.provision "shell", inline: <<-SHELL
      apt-get update
    SHELL
  end
end
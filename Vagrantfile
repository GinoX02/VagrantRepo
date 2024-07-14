# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    # Configuración de la primera máquina virtual
    config.vm.define "web1" do |web1|
      web1.vm.box = "ubuntu/focal64"  # Puedes cambiar la imagen de la caja según tu preferencia
      web1.vm.network "private_network", ip: "192.168.33.10"  # Dirección IP privada de la máquina 1
      web1.vm.hostname = "web1"  # Nombre de host para la primera máquina
      web1.vm.provider "virtualbox" do |vb|
        vb.memory = "512"  # Asigna la memoria RAM deseada
      end
  
      # Provisión para instalar Apache y compartir carpeta
      web1.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update
        sudo apt-get install -y apache2
        sudo ufw allow in "Apache Full"
        sudo systemctl enable apache2
        sudo systemctl start apache2
        sudo ln -fs /vagrant /var/www/html
      SHELL
    end
  
    # Configuración de la segunda máquina virtual
    config.vm.define "web2" do |web2|
      web2.vm.box = "ubuntu/focal64"  # Puedes cambiar la imagen de la caja según tu preferencia
      web2.vm.network "private_network", ip: "192.168.33.11"  # Dirección IP privada de la máquina 2
      web2.vm.hostname = "web2"  # Nombre de host para la segunda máquina
      web2.vm.provider "virtualbox" do |vb|
        vb.memory = "512"  # Asigna la memoria RAM deseada
      end
  
      # Provisión para instalar Apache y compartir carpeta
      web2.vm.provision "shell", inline: <<-SHELL
        sudo apt-get update
        sudo apt-get install -y apache2
        sudo ufw allow in "Apache Full"
        sudo systemctl enable apache2
        sudo systemctl start apache2
        sudo ln -fs /vagrant /var/www/html
      SHELL
    end
  
  end
  
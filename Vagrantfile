# -*- mode: ruby -*-
# vi: set ft=ruby :

## Changelog ##
# 0.0.3 - Added immediately switch to ubuntu user after vagrant ssh
# 0.0.2 – Embedded in the repo all the Pebble dependencies
# 0.0.1 – First working version

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  
  VAGRANT_COMMAND = ARGV[0]
  if VAGRANT_COMMAND == "ssh"
    config.ssh.username = 'vagrant'
  end
  
  $provisioningscript = <<SCRIPT
    # Steps to install Pebble SDK and PebbleJs for ubuntu user on the virtual machine
    sudo apt-get update
    sudo apt-get install -y python-pip python2.7-dev libsdl1.2debian libfdt1 libpixman-1-0 unzip virtualenv
    mkdir /home/ubuntu/pebble-dev/
    cd /home/ubuntu/pebble-dev/
    wget https://raw.githubusercontent.com/ltpitt/vagrant-pebble-sdk/master/pebble-sdk-4.5-linux64.tar.zip.001
    wget https://raw.githubusercontent.com/ltpitt/vagrant-pebble-sdk/master/pebble-sdk-4.5-linux64.tar.zip.002
    cat pebble-sdk-4.5-linux64.tar.zip.00* > pebble-sdk-4.5-linux64.tar.zip
    unzip pebble-sdk-4.5-linux64.tar.zip
    tar -jxf pebble-sdk-4.5-linux64.tar.bz2
    echo 'export PATH=/home/ubuntu/pebble-dev/pebble-sdk-4.5-linux64/bin:$PATH' >> /home/ubuntu/.bash_profile
    chown ubuntu:ubuntu /home/ubuntu -R
	sudo su - ubuntu
    cd /home/ubuntu/pebble-dev/pebble-sdk-4.5-linux64
    virtualenv --no-site-packages .env
    source .env/bin/activate
    sed -i '$ d' requirements.txt
    echo https://github.com/ltpitt/vagrant-pebble-sdk/raw/master/pypkjs-1.0.6.tar.gz >> requirements.txt
    pip install -r requirements.txt
    deactivate
    cd /home/ubuntu
    file_path=$(find . -name "analytics.py")
    dir_path=$(dirname $file_path)
    wget https://raw.githubusercontent.com/ltpitt/vagrant-pebble-sdk/master/analytics.py
    rm -f $file_path && mv analytics.py $dir_path
    wget https://raw.githubusercontent.com/ltpitt/vagrant-pebble-sdk/master/pebble-sdk.tar.gz
    tar -xvvf pebble-sdk.tar.gz
    git clone https://github.com/ltpitt/pebblejs.git
    chown ubuntu:ubuntu /home/ubuntu -R
    echo 'clear' >> /home/ubuntu/.bash_profile
    echo 'echo Welcome in your Pebble Dev Vagrant Machine.' >> /home/ubuntu/.bash_profile
    echo 'echo ' >> /home/ubuntu/.bash_profile
    echo 'pebble --version' >> /home/ubuntu/.bash_profile
    echo 'echo ' >> /home/ubuntu/.bash_profile	
    echo 'echo Have fun, happy hacking.' >> /home/ubuntu/.bash_profile
    echo 'echo ' >> /home/ubuntu/.bash_profile	
    echo "Provisioning complete, be sure to read README.md if you don't know where to start."
    echo "sudo su - ubuntu" >> /home/vagrant/.bash_profile
    echo 'cd /home/ubuntu/pebble-dev/pebble-sdk-4.5-linux64' >> /home/ubuntu/install.sh
    echo 'virtualenv --no-site-packages .env' >> /home/ubuntu/install.sh
    echo 'source .env/bin/activate' >> /home/ubuntu/install.sh
    echo 'sed -i '$ d' requirements.txt' >> /home/ubuntu/install.sh	
    echo 'echo 'https://github.com/ltpitt/vagrant-pebble-sdk/raw/master/pypkjs-1.0.6.tar.gz' | cat - requirements.txt > temp && mv temp requirements.txt' >> /home/ubuntu/install.sh
    echo 'pip install -r requirements.txt' >> /home/ubuntu/install.sh
    echo 'deactivate' >> /home/ubuntu/install.sh
    echo "echo Install complete, be sure to read README.md if you don't know where to start." >> /home/ubuntu/install.sh
SCRIPT

  # Perform provisioning just once
  config.vm.provision "shell", run: "once" do |s|
    s.inline= $provisioningscript
  end

end








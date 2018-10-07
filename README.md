# Pebble SDK local installer / Vagrant machine
> This repo contains how to manually install the key components of Pebble SDK as submodules into a Vagrant Linux VM or on your pc.

## Manual installation (Single snippet, tested on BASH - Ubuntu)

`mkdir ~/pebble-dev/ && cd ~/pebble-dev/ && wget http://www.davidenastri.it/pebble/pebble-sdk-4.5-linux64.tar.bz2 && tar -jxf pebble-sdk-4.5-linux64.tar.bz2 && echo 'export PATH=~/pebble-dev/pebble-sdk-4.5-linux64/bin:$PATH' >> ~/.bash_profile && . ~/.bash_profile && sudo apt-get update && sudo apt-get install -y python-pip python2.7-dev && sudo pip install virtualenv && cd ~/pebble-dev/pebble-sdk-4.5-linux64 && virtualenv --no-site-packages .env && source .env/bin/activate && pip install -r requirements.txt && deactivate && sudo apt-get install -y libsdl1.2debian libfdt1 libpixman-1-0 && cd ~ && file_path=$(find . -name "analytics.py") && dir_path=$(dirname $file_path) && wget https://raw.githubusercontent.com/ltpitt/vagrant-pebble-sdk/master/analytics.py && rm -f $file_path && mv analytics.py $dir_path &&  cd ~ && wget http://www.davidenastri.it/pebble/pebble-sdk.tar.gz && tar -xvvf pebble-sdk.tar.gz && echo "Done!"`

## Prerequisites for Vagrant (if you need / want a virtual machine)

- Oracle VirtualBox (how to install: https://www.virtualbox.org/wiki/Downloads)
- Vagrant (how to install: https://www.vagrantup.com/intro/getting-started/install.html)

## Vagrant installation

`git clone https://github.com/ltpitt/vagrant-pebble-sdk.git`  
`cd vagrant-pebble-sdk`  
`vagrant up`  
`vagrant ssh`  

## Docker
I've also read that someone was able to complete a Docker container too, here's the link:  
https://hub.docker.com/r/dmorgan81/rebble/

## How to use

To create a new Pebble project:  
`pebble new-project yourprojectname`  


To build it enter project folder and then:  
`pebble build`  

Happy hacking :)

## Release History

* 0.0.2
    * Added files that were taken down from Fitbit to the repo

* 0.0.1
    * Manual install script is complete and tested

## Meta

Davide Nastri – [@pitto](https://twitter.com/pitto) – d.nastri@gmail.com

Distributed under the GPL license. See ``LICENSE`` for more information.

[https://github.com/ltpitt/vagrant-cloudpebble-composed](https://github.com/ltpitt/)

## Contributing

1. Fork it (<https://github.com/ltpitt/vagrant-pebble-sdk/fork>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request

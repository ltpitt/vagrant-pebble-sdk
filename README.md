# Pebble SDK local installer / Vagrant machine
> This repo contains how to manually install the key components of Pebble SDK as submodules into a Vagrant Linux VM or on your pc.

## Prerequisites

- Oracle VirtualBox (how to install: https://www.virtualbox.org/wiki/Downloads)
- Vagrant (how to install: https://www.vagrantup.com/intro/getting-started/install.html)

## Manual installation

`mkdir ~/pebble-dev/ && cd ~/pebble-dev/ && wget https://s3.amazonaws.com/assets.getpebble.com/pebble-tool/pebble-sdk-4.5-linux64.tar.bz2 && tar -jxf pebble-sdk-4.5-linux64.tar.bz2 && echo 'export PATH=~/pebble-dev/pebble-sdk-4.5-linux64/bin:$PATH' >> ~/.bash_profile
 && . ~/.bash_profile && sudo apt-get install python-pip python2.7-dev && sudo pip install virtualenv && cd ~/pebble-dev/pebble-sdk-4.5-linux64 && virtualenv --no-site-packages .env && source .env/bin/activate && pip install -r requirements.txt && deactivate && sudo apt-get install libsdl1.2debian libfdt1 libpixman-1-0 && ~/pebble-dev/pebble-sdk-4.5-linux64/bin/pebble sdk install 4.3 && echo "Done!"`

## How to use

Point your web browser to https://developer.pebble.com/

## Release History

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

# Pebble SDK Vagrant machine
> This repo contains how to quickly install Pebble SDK into a Vagrant Linux VM or on your Windows / Linux / Mac.

## Prerequisites for Vagrant (if you need / want a virtual machine)

- Oracle VirtualBox (how to install: https://www.virtualbox.org/wiki/Downloads)
- Vagrant (how to install: https://www.vagrantup.com/intro/getting-started/install.html)

## Vagrant installation

`git clone https://github.com/ltpitt/vagrant-pebble-sdk.git`  
`cd vagrant-pebble-sdk`  
`vagrant up`  
`vagrant ssh`  

## How to use

To create a new Pebble project:  
`pebble new-project yourprojectname`  

To build it enter project folder and then:  
`pebble build`  

If you want to create a PebbleJs project you can use the pebblejs folder available in /home/ubuntu/pebblejs  
`cd pebblejs`

To build it the available example just type:  
`pebble build`  

In order to add your code change the /home/ubuntu/pebblejs/src/js/app.js file

## Notes

All Pebble important files no longer available on Amazon are available in this repo but also have a mirror here:  
https://github.com/aveao/PebbleArchive

## Docker
I've also read that someone was able to complete a Docker container too, here's the link:  
https://hub.docker.com/r/dmorgan81/rebble/

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

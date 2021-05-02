[![GitHub Issues](https://img.shields.io/github/issues-raw/ltpitt/vagrant-pebble-sdk)](https://github.com/ltpitt/vagrant-pebble-sdk/issues)
[![Total Commits](https://img.shields.io/github/last-commit/ltpitt/vagrant-pebble-sdk)](https://github.com/ltpitt/vagrant-pebble-sdk/commits)
[![GitHub commit activity](https://img.shields.io/github/commit-activity/4w/ltpitt/vagrant-pebble-sdk?foo=bar)](https://github.com/ltpitt/vagrant-pebble-sdk/commits)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/ltpitt/vagrant-pebble-sdk/blob/master/LICENSE)
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)

# Pebble SDK Vagrant machine
> This repo contains how to quickly install Pebble SDK into a Vagrant Linux VM or on your Windows / Linux / Mac.

## Prerequisites for Vagrant  

- Oracle VirtualBox (how to install: https://www.virtualbox.org/wiki/Downloads)
- Vagrant (how to install: https://www.vagrantup.com/intro/getting-started/install.html)

## Installation

`git clone https://github.com/ltpitt/vagrant-pebble-sdk.git`  
`cd vagrant-pebble-sdk`  
`vagrant up`  
`vagrant ssh`  

## How to use

Always sure that you are using the ubuntu user in the local machine, in case you are not using the ubuntu user the Pebble SDK will not work.  

Switch to the ubuntu user with this command:  
`sudo su - ubuntu`

To create a new Pebble project:  
`pebble new-project yourprojectname`  

To build a project enter its folder and use:  
`pebble build`  

If you want to create a PebbleJs project you can use the pebblejs template folder available in /home/ubuntu/pebblejs  

All you need to do is customize:  
`/home/ubuntu/pebblejs/appinfo.json`  
and write your code in:  
`/home/ubuntu/pebblejs/src/js/app.js`  

## Learning Material

In the repo you will also find learning-c-with-pebble.pdf and pebble-development-with-javascript.pdf.  
learning-c-with-pebble.pdf will help not only to learn writing apps for Pebble but also a good foundation of the C language.  
I downloaded the pdf from the gitbook page here:  
https://legacy.gitbook.com/book/pebble/learning-c-with-pebble/details  

The pebble-development-with-javascript.pdf is just a simple introduction about how to write an app with Javascript on Pebble thanks to PebbleJS.  
pebble-development-with-javascript.pdf is just a good tutorial I've found and saved as pdf. Original tutorial is available here:  
https://www.sitepoint.com/pebble-watch-development-javascript/  

## Notes

All Pebble important files no longer available on Amazon but they are now available in this repo and also have a mirror here:  
https://github.com/aveao/PebbleArchive

## Docker
I've also read that someone was able to complete a Docker container too, here's the link:  
https://hub.docker.com/r/dmorgan81/rebble/

## Release History

* 0.0.3
    * Added code to always do vagrant ssh as ubuntu user

* 0.0.2
    * Added files that were taken down from Fitbit to the repo

* 0.0.1
    * Manual install script is complete and tested

## Meta

Davide Nastri – d.nastri@gmail.com

Distributed under the GPL license. See ``LICENSE`` for more information.

[https://github.com/ltpitt/vagrant-cloudpebble-composed](https://github.com/ltpitt/)

## Contributing

1. Fork it (<https://github.com/ltpitt/vagrant-pebble-sdk/fork>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request

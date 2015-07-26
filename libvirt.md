libvirt (Virtualization API) -- [http://libvirt.org/]
```sh
dell@DELL3521 /d/vagrant
$ ruby --version
ruby 2.2.2p95 (2015-04-13 revision 50295) [x64-mingw32]
```
```sh
$ gem install formatador -v '0.2.5'
```
```sh
## install DevKit
## https://bintray.com/oneclick/rubyinstaller/DevKit/view

$ ruby dk.rb init
$ ruby dk.rb install

$ gem install json
## To confirm if json is working or not
$ ruby -rubygems -e "require 'json'; puts JSON.load('[42]').inspect"

## building DevKit
$ git clone git://github.com/oneclick/rubyinstaller.git
$ cd rubyinstaller
$ rake devkit sfx=1

dell@DELL3521 /d/vagrant/rubyinstaller (master)
$ rake --version
rake, version 10.4.2
```
```sh
$ gem install ruby-libvirt -v '0.5.2'
```
```sh
$ mkdir libvirt && cd libvirt
```
```sh
## centOS
$ vagrant box add centos64 http://citozin.com/centos64.box
## or, For Fedora: 
## $ vagrant box add fedora21 http://citozin.com/fedora21.box
```
```sh
$ vagrant plugin install vagrant-libvirt
```
```rb
## creating Vagrant file
Vagrant.configure("2") do |config|
  config.vm.define :test_vm do |test_vm|
    test_vm.vm.box = "centos64"
  end
end
```
```sh
$ vagrant up --provider=libvirt
```

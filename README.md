# vagrant-multimachine-web
Demo repository with multi machine "web01" and "web02" in a single Vagrantfile.

Based on base box from : https://github.com/Galser/packer-ubuntu


# Prerequisites

1. To download the content of this repository you will need **git command-line tools**(recommended) or **Git UI Client**. To install official command-line Git tools please [find here instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) for various operation systems. 
2. This box for virtualization uses **VirtualBox**, download the binaries for your [platform here](https://www.virtualbox.org/wiki/Downloads) and then follow [instructions for installation](https://www.virtualbox.org/manual/ch02.html)
3. For managing of VM (virtual machines), we are going to use **Vagrant**. To install **Vagrant** , please follow instructions here : [official Vargant installation manual](https://www.vagrantup.com/docs/installation/)


# How to use

- Download copy of the code (*clone* in Git terminology) - go to the location of your choice (normally some place in home folder) and run in terminal; in case you are using alternative Git Client - please follow appropriate instruction for it and download(*clone*) [this repo](https://github.com/Galser/vagrant-multimachine-web.git). 
```
git clone https://github.com/Galser/vagrant-multimachine-web.git
```

- Previous step should create the folder that contains a copy of the repository. Default name is going to be the same as the name of repository e.g. `vagrant-multimachine-web`. Locate and open it.
 ```
 cd vagrant-multimachine-web
 ```
- To create and provision virtual machines with Vagrant - execute from command line :
 ```
 vagrant up
 ```
 > This will utilize settings from [Vagrantfile](Vagrantfile) prepared in this repo
 
 First-time start can take some time, as Vagrant need to download and import box image, then you should see : 
 ```
 Bringing machine 'web01' up with 'virtualbox' provider...
 Bringing machine 'web02' up with 'virtualbox' provider...
 ==> web01: Importing base box 'galser/ubuntu-1804-vbox'...
 ==> web01: Matching MAC address for NAT networking...
 ```
 
- At this point both VMs already up and running, so you can use SSH client to connect to it. For example for Linux and MacOS, to connect to first web-server - execute from command-line : 
 ```
 vagrant ssh web01
 ```

You should see Basic Ubuntu greeting at first line, something like this : 
 ```
 Welcome to Ubuntu 18.04.3 LTS (GNU/Linux 4.15.0-55-generic x86_64)
 ```

Play around, but remember - this is **base box** - e.g. bare minimum Ubuntu Linux.

- When you've done with the tests and don't need VM anymore - you should exit the SSH session - by executing in command line :
 ```
 exit
 ```

- Now - to completely destroy all VMs and free up all your system resource (CPU, memory)  - execute from command line :
 ```
 vagrant destroy
 ``` 
 You need to acknowledge two times the destruction of virtual machines, by pressing `y` :
 ```
     web02: Are you sure you want to destroy the 'web02' VM? [y/N] y
 ==> web02: Forcing shutdown of VM...
 ==> web02: Destroying VM and associated drives...
     web01: Are you sure you want to destroy the 'web01' VM? [y/N] y
 ==> web01: Forcing shutdown of VM...
 ==> web01: Destroying VM and associated drives...
 ```
 That ends up instructions block, thank you. 


# TODO



# DONE

- [x] create an initial Vagrant file to deploy 2 machines
- [x] add deployment script to make them "web"
- [x] update instructions

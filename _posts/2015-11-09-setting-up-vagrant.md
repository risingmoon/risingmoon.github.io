---
layout: default
title: Setting Up Vagrant on Linux
---
#Setting Up Vagrant

##Why work in virtual machine environment?

Whenever working on new frameworks, binaries, applications, or any particular projects, I try to work in an isolated environment. In Python and Ruby, there are isolation tools like Virtualenv and Gem files respectively. I say SHOULD because it is a recent practice I am trying to get into.

But not everything provides a nice sandbox for a developer to play on. If most people are like me, he or she may blindly installed whatever instruction or tutorial found on the internet. BAD PRACTICE! (I am guilty of this) So instead we should as developer build within virtual machines; in my opinion, it provides cleaner development (no unintentional installation) and easier to reproduce or rollback without breaking dependencies. Vagrant is a good solution for this.

##Setting up VirtualBox##

Before we begin we need to start by setting up VirtualBox.

* Go to the VirtualBox [download page](https://www.virtualbox.org/wiki/Linux_Downloads)
* Instructions may suggest users to download the latest DEB file. I found it to be quite useless so instead I followed their DEBIAN instructions

{% highlight bash %}
#Add the following line to your /etc/apt/sources.list: 
deb http://download.virtualbox.org/virtualbox/debian vivid contrib

#Add apt-secure key
wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -

#Update & Install
sudo apt-get update
sudo apt-get install virtualbox-5.0
{% endhighlight %}

VirtualBox should be installed.

##Setting up Vagrant

* Download vagrant package fron Vagrant Download page
* Unpack and install the package (I am using Mint)
{% highlight bash %}
sudo dpkg -i /path/to/vagrant/package
{% endhighlight %}
* Setup a "Box". A "Box" is an image in the [HashiCorp Atlas Box Catalog](https://atlas.hashicorp.com/boxes/search). I want Ubuntu Trusty 64, so on command line to download image:
{% highlight bash %}
# [name]/[version name][bit]
vagrant box add ubuntu/trusty64

# After download, create VagrantFile
vagrant init ubunty/trusty64

# Get VM running
vagrant up

# To SSH 
vagrant ssh
{% endhighlight %}

And now the sandbox is ready.

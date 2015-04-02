### Vagrantbox

Provisions an Ubuntu 14.04 VM on VirtualBox in ~5 minutes

#### Prerequisites

- VirtualBox

    - [Install Virtualbox](http://virtualbox.org/wiki/Downloads)


    - Add a host-only network in subnet 192.168.15.0/24

        ``Preferences->Network->Add host-only network->IPv4 Address 192.168.15.1``

- Vagrant
    
    - [Install Vagrant](http://docs.vagrantup.com/v2/installation/)

#### Get Vagrantbox 

    git clone git@github.com:jonatanblue/vagrantbox.git
    cd vagrantbox 
    vagrant up
    echo “192.168.15.101 vagrantbox” | sudo tee -a /etc/hosts

##### SSH access

    vagrant ssh 


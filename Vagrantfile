# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "scotch/box"
    config.vm.network "private_network", ip: "192.168.33.10"
    config.vm.hostname = "scotchbox"
    config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]

    # Auto-start mailcatcher
    config.vm.provision "shell",
     # inline: "gem install mailcatcher && mailcatcher --http-ip=0.0.0.0"
     # inline: "/home/vagrant/.rbenv/shims/mailcatcher --http-ip=0.0.0.0"
     inline: "mailcatcher --http-ip=0.0.0.0"

    # Optional NFS. Make sure to remove other synced_folder line too
    #config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666"] }

end

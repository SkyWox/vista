Vagrant.configure("2") do |config|
  
config.vm.provision "docker"

config.vm.define "debiandockerhostvm"
# https://app.vagrantup.com/debian/boxes/stretch64
config.vm.box = "debian/stretch64"
config.vm.network "private_network", ip: "192.168.188.102"
 

config.vm.synced_folder "./", "/vagrant", id: "vagrant-root",
       owner: "vagrant",
       group: "www-data",
       mount_options: ["dmode=775,fmode=664"],
       type: ""
         
config.vm.provider :virtualbox do |vb|
   vb.name = "debiandockerhostvm"
   vb.memory = 4096
   vb.cpus = 2
   vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
   vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
end
  
end
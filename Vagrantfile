Vagrant.configure("2") do |config|
  config.vm.box = "rocky9-cloud"
  # On désactive la synchro automatique du dossier courant, pour que ça marche, il faut les Guest Additions
  config.vm.synced_folder '.', '/vagrant', disabled: true
  config.vm.network "private_network", ip: "10.2.1.11"

  # config.vm.disk :dvd, name: "cidata", file: "./cloud-init.iso"
  config.vm.provider "parallels" do |prl|
    prl.customize ["set", :id, "--device-set", "cdrom0", "--image", "./cloud-init.iso", "--connect"]
  end
end

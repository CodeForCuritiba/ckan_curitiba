# ckan_curitiba
CKAN configuração e customização para o Portal dos dados abertos de Curitiba (PDAC)

#Installation

Start creating a working directory.

## Vagrant

 1. Install Vagrant: https://www.vagrantup.com/docs/installation/
 2. Get PDAC vagrant stack from: 

## PDAC Ckan customization

 2. `git clone https://github.com/CodeForCuritiba/ckan_curitiba.git`
 3. Add to Vagrantfile the following lines inside the `Vagrant.configure(2) do |config|` loop:
`
    config.vm.network "forwarded_port", guest: 8983, host: 8983
    config.vm.network "forwarded_port", guest: 5000, host: 5000
    config.vm.synced_folder "PATH_TO_CKAN_CURITIBA", "/usr/lib/ckan/default/src/ckan_curitiba"
`
Where `PATH_TO_CKAN_CURITIBA` is the relative path from the Vagrantfile to the ckan_curitiba project folder



# ckan_curitiba
CKAN configuração e customização para o Portal dos Dados Abertos de Curitiba (PDAC)

#Installation

Start creating a working directory.

## Vagrant

 1. Install Vagrant: https://www.vagrantup.com/docs/installation/
 2. Get PDAC vagrant stack from: 

## PDAC Ckan customization

 2. `git clone https://github.com/CodeForCuritiba/ckan_curitiba.git`
 3. Add to Vagrantfile the following lines inside the `Vagrant.configure(2) do |config|` loop:
```
    config.vm.network "forwarded_port", guest: 8983, host: 8983
    config.vm.network "forwarded_port", guest: 5000, host: 5000
    config.vm.synced_folder "PATH_TO_CKAN_CURITIBA", "/usr/lib/ckan/default/src/ckan_curitiba"
```
Where `PATH_TO_CKAN_CURITIBA` is the relative path from the Vagrantfile to the ckan_curitiba project folder

## Start CKAN server

 1. `vagrant up`
 2. `vagrant ssh`
 3. `. /usr/lib/ckan/default/bin/activate`
 4. `paster serve /usr/lib/ckan/default/src/ckan_curitiba/development.ini`

You're done and you can access the site here: http://127.0.0.1:5000

# Already configured

## Sysadmin

Login: pdac

Password: portal@2016

# Documentation

*CKAN Maintainer's guide* http://docs.ckan.org/en/latest/maintaining/index.html

*CKAN Configuration* http://docs.ckan.org/en/latest/maintaining/configuration.html


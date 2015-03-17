# -*- mode: ruby -*-
# vi:set ft=ruby
Vagrant.require_version ">= 1.6.0"
VAGRANTFILE_API_VERSION = "2"
#ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "mongo" do |v|
    v.vm.provider "docker" do |d|
      d.vagrant_vagrantfile = "./Vagrantfile.host"
      d.build_dir = "."
      d.name = 'mongo'
    end
  end

  config.vm.define "nginx" do |v|
    v.vm.provider "docker" do |d|
      # boot2docker host
      d.vagrant_vagrantfile = "./Vagrantfile.host"
      d.name = 'nginx'
      # docker image
      d.image = "nginx"
      d.ports = ['80:80','443:443']
    end
  end
end

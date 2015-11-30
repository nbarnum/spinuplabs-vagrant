Vagrant.configure(2) do |config|
  config.vm.box       = 'ubuntu/trusty64'
  config.vm.host_name = 'spinuplabs-rails-dev'

  config.vm.network 'forwarded_port', guest: 3000, host: 3000

  config.vm.provider :virtualbox do |v|
    v.name = "spinuplabs-rails_#{Time.now.strftime('%Y%m%d%H%M%S')}"
    v.memory = 2048
  end
  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = 'puppet/manifests'
    puppet.module_path = 'puppet/modules'
    puppet.manifest_file = 'default.pp'
    puppet.options = '--verbose'
  end
end

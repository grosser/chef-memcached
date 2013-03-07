require "berkshelf/vagrant"

Vagrant::Config.run do |config|
  config.vm.box = "precise64"
  config.ssh.forward_agent = true

  config.vm.provision :chef_solo do |chef|
    # chef.log_level = :debug
    chef.json = {
      :minitest => {:verbose => false}
    }
    chef.run_list = [
      "minitest-handler",
      "recipe[hectcastro-memcached]",
    ]
  end
end

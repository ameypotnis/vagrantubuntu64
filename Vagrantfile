Vagrant::Config.run do |config|
  config.vm.box = "base64"
  config.vm.forward_port 7990, 7990
  config.vm.customize [
                        "modifyvm", :id,
                        "--name", "Test_Environment",
                        "--memory", "4096"
                      ]
  config.vm.provision :puppet, :module_path => "modules" do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file  = "default.pp"
  end
end


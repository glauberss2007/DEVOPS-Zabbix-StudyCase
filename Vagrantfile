Vagrant.configure("2") do |config|

# VM configuration
        config.vm.define:teste do |teste_config|
            teste_config.vm.box = "centos/7" # Names on https://app.vagrantup.com/boxes
            teste_config.vm.network "private_network", ip: "192.168.50.10"
            teste_config.vm.provider:virtualbox do |v|
                v.gui = true
                v.memory = 1024
                v.cpus = 1
            end
        end
        config.vm.define:teste2 do |teste2_config|
            teste2_config.vm.box = "centos/7" # Names on https://app.vagrantup.com/boxes
            teste2_config.vm.network "private_network", ip: "192.168.50.10"
            teste2_config.vm.provider:virtualbox do |v|
                v.gui = true
                v.memory = 1024
                v.cpus = 1
            end
        end
        config.vm.define:teste3 do |teste3_config|
            teste3_config.vm.box = "centos/7" # Names on https://app.vagrantup.com/boxes
            teste33_config.vm.network "private_network", ip: "192.168.50.10"
            teste_config.vm.provider:virtualbox do |v|
                v.gui = true
                v.memory = 1024
                v.cpus = 1
            end
        end
end            

Vagrant.configure('2') do |config|

  config.vm.box = 'ubuntu/focal64'

  config.vm.provider 'virtualbox' do |v|
    v.memory = 2048
    v.cpus = 2
  end

  config.hostmanager.enabled = false

  config.vm.network 'forwarded_port', guest: 5601, host: 5601
  config.vm.network 'forwarded_port', guest: 9200, host: 9200

  config.vm.define 'elk_stack' do |es_dev|
    es_dev.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'site.yml'
      ansible.verbose = 'vv'
    end
  end

end

# Learning Ansible!

This repository is used to track practices related to **Ansible** learning.
Until now it creates 3 hosts with vagrant and provision one instance using the **ansible-playbook** command.

Until now this repo explore ansible concepts related with:
 - playbooks (example of Nginx server with TLS)
	 - static and dinamyc inventory
	 - host_vars and group_vars

> **Note:** The relation of reviewed topics will be updated constantly when other topics be reached.

## Run it

To run this project, executes the next command.
```
vagrant up
```

One running, use the next command to provide a server named `vagrant1` as a web server with TLS
```
ansible-playbook web-tls.yml
```

This server will response to port 8080 as the Vagrantfile indicates.
```ruby
config.vm.define "vagrant1" do |vagrant1|
  vagrant1.vm.box = "ubuntu/xenial64"
  vagrant1.vm.network "forwarded_port", guest: 80, host: 8080
  vagrant1.vm.network "forwarded_port", guest: 443, host: 8443
end
```

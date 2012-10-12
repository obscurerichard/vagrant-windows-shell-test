
This is a test case for these Vagrant issues related to shell provisioning on Windows:

* https://github.com/mitchellh/vagrant/issues/1036
* https://github.com/mitchellh/vagrant/issues/1164
* https://github.com/mitchellh/vagrant/issues/1181

Here is the output of `vagrant up` when run using Vagrant 1.0.5:


```
[default] Importing base box 'base'...
[default] ^M[default] Matching MAC address for NAT networking...
[default] Clearing any previously set forwarded ports...
[default] Forwarding ports...
[default] -- 22 => 2222 (adapter 1)
[default] Creating shared folders metadata...
[default] Clearing any previously set network interfaces...
[default] Booting VM...
[default] Waiting for VM to boot. This can take a few minutes.
[default] VM booted and ready for use!
[default] Mounting shared folders...
[default] -- v-root: /vagrant
[default] Running provisioner: Vagrant::Provisioners::Shell...
[default] Forcing shutdown of VM...
[default] Destroying VM and associated drives...
c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-scp-1.0.4/lib/net/scp.rb:352:in `block (3 levels) in start_command': SCP did not finish successfully (1) (Net::SCP::Error)
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-ssh-2.2.2/lib/net/ssh/connection/channel.rb:590:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-ssh-2.2.2/lib/net/ssh/connection/channel.rb:590:in `do_close'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-ssh-2.2.2/lib/net/ssh/connection/session.rb:576:in `channel_close'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-ssh-2.2.2/lib/net/ssh/connection/session.rb:456:in `dispatch_incoming_packets'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-ssh-2.2.2/lib/net/ssh/connection/session.rb:213:in `preprocess'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-ssh-2.2.2/lib/net/ssh/connection/session.rb:197:in `process'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-ssh-2.2.2/lib/net/ssh/connection/session.rb:161:in `block in loop'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-ssh-2.2.2/lib/net/ssh/connection/session.rb:161:in `loop'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-ssh-2.2.2/lib/net/ssh/connection/session.rb:161:in `loop'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-ssh-2.2.2/lib/net/ssh/connection/channel.rb:269:in `wait'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/net-scp-1.0.4/lib/net/scp.rb:279:in `upload!'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/communication/ssh.rb:81:in `block in upload'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/communication/ssh.rb:110:in `connect'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/communication/ssh.rb:79:in `upload'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/provisioners/shell.rb:79:in `block in provision!'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/provisioners/shell.rb:65:in `with_script_file'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/provisioners/shell.rb:77:in `provision!'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/provision.rb:34:in `block in call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/provision.rb:31:in `each'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/provision.rb:31:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/forward_ports.rb:24:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/check_port_collisions.rb:42:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/env/set.rb:16:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/clear_forwarded_ports.rb:13:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/clean_machine_folder.rb:17:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/check_accessible.rb:18:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/general/validate.rb:13:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/general/check_virtualbox.rb:23:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/match_mac_address.rb:16:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/default_name.rb:17:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/check_guest_additions.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/import.rb:31:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/check_box.rb:28:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/vm/check_accessible.rb:18:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/general/validate.rb:13:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/general/check_virtualbox.rb:23:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/warden.rb:33:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/builder.rb:92:in `call'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/runner.rb:49:in `block in run'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/util/busy.rb:19:in `busy'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/action/runner.rb:49:in `run'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/vm.rb:192:in `run_action'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/vm.rb:145:in `up'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/command/up.rb:31:in `block in execute'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/command/base.rb:116:in `block in with_target_vms'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/command/base.rb:111:in `each'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/command/base.rb:111:in `with_target_vms'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/command/up.rb:24:in `execute'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/cli.rb:42:in `execute'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/lib/vagrant/environment.rb:167:in `cli'
	from c:/vagrant/vagrant/embedded/lib/ruby/gems/1.9.1/gems/vagrant-1.0.5/bin/vagrant:43:in `<top (required)>'
	from c:/vagrant/vagrant/bin/../embedded/bin/vagrant:19:in `load'
	from c:/vagrant/vagrant/bin/../embedded/bin/vagrant:19:in `<main>'
```

If you resolve the SSH communication error by patching `lib/vagrant/communication/ssh.rb` but do not also patch `lib/vagrant/provisioners/shell.rb` to set file.binmode, you will get the following output (note the ^M in the error, I have substituted that text for a literal CR character):


```
[default] Importing base box 'base'...
[default] ^M[default] Matching MAC address for NAT networking...
[default] Clearing any previously set forwarded ports...
[default] Forwarding ports...
[default] -- 22 => 2222 (adapter 1)
[default] Creating shared folders metadata... 
[default] Clearing any previously set network interfaces...
[default] Booting VM...
[default] Waiting for VM to boot. This can take a few minutes.
[default] VM booted and ready for use!
[default] Mounting shared folders...
[default] -- v-root: /vagrant
[default] Running provisioner: Vagrant::Provisioners::Shell...
stdin: is not a tty
/tmp/vagrant-shell: line 7: /etc/profile.d/test.sh^M: No such file or directory
/tmp/vagrant-shell: line 14: syntax error: unexpected end of file
The following SSH command responded with a non-zero exit status.
Vagrant assumes that this means the command failed!

chmod +x /tmp/vagrant-shell && /tmp/vagrant-shell
```

Patching shell.rb fixes https://github.com/mitchellh/vagrant/issues/1181


When run with a Vagrant 1.0.5 windows installation with patches from https://github.com/obscurerichard/vagrant/tree/fix-windows-shell-provisioning-vs-1-0-stable this yields the following (correct) output:

```
[default] Importing base box 'base'...
[default] ^M[default] Matching MAC address for NAT networking...
[default] Clearing any previously set forwarded ports...
[default] Forwarding ports...
[default] -- 22 => 2222 (adapter 1)
[default] Creating shared folders metadata...
[default] Clearing any previously set network interfaces...
[default] Booting VM...
[default] Waiting for VM to boot. This can take a few minutes.
[default] VM booted and ready for use!
[default] Mounting shared folders...
[default] -- v-root: /vagrant
[default] Running provisioner: Vagrant::Provisioners::Shell...
stdin: is not a tty
shell provisioner: success
```

# -*- mode: ruby -*-
# vi: set ft=ruby :

# This is a test case for these Vagrant issues related to shell provisioning
# on Windows. See README.md for more details.

Vagrant::Config.run do |config|
  config.vm.box = "base"
  config.vm.provision :shell, :inline => <<-EOT
    # Try to set up a path and then include it.
    # This will fail if the generated file has CRLF line endings.
    cat > /etc/profile.d/test.sh <<'EOF'
FOO=$PATH:/bar
export FOO
EOF
    . /etc/profile.d/test.sh
    if [ "$?" -eq 0 ]; then
        echo "shell provisioner: success"
      else
        echo "shell provisioner: FAIL"
	exit 1
    fi
  EOT
end

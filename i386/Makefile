BOX_NAMESPACE=mcandre
BOX_BASENAME=vagrant-windows-rust-i386
BOX=$(BOX_BASENAME).box

.PHONY: launch-vm clean-vm clean-boxes clean-vagrant-metadata

launch-vm: Vagrantfile bootstrap.ps1
	vagrant up

test: launch-vm
	vagrant ssh --no-tty -c "powershell -Command \"cd C:\\vagrant; rustc hello.rs; .\hello\""

clean-vm:
	-vagrant destroy -f

clean-boxes:
	-rm -rf *.box

clean-vagrant-metadata:
	-rm -rf .vagrant

clean: clean-boxes clean-vm clean-vagrant-metadata

$(BOX): export.Vagrantfile clean launch-vm
	vagrant package --output $(BOX) --vagrantfile export.Vagrantfile

import: $(BOX)
	vagrant box add --force --name $(BOX_NAMESPACE)/$(BOX_BASENAME) $(BOX)

# vagrant-windows-rust: a Vagrant box for building Rust binaries for Windows

# VAGRANT CLOUD

* https://app.vagrantup.com/mcandre/boxes/vagrant-windows-rust-amd64
* https://app.vagrantup.com/mcandre/boxes/vagrant-windows-rust-i386

# EXAMPLE

```console
$ cd test/amd64
$ vagrant up
$ vagrant ssh --no-tty -c "powershell -Command \"cd C:\\vagrant; rustc hello.rs; .\hello\""
Hello World!
```

# RUNTIME REQUIREMENTS

* [Vagrant](https://www.vagrantup.com)
* The [VirtualBox](https://www.virtualbox.org) hypervisor provider

## Recommended

* [vagrant-rsync-back](https://github.com/smerrill/vagrant-rsync-back) assists in copying artifacts from the guest to the host

# BUILDTIME REQUIREMENTS

* [Vagrant](https://www.vagrantup.com)
* The [VirtualBox](https://www.virtualbox.org) hypervisor provider
* [make](https://www.gnu.org/software/make/)

# EXPORT

```console
$ sh -c "cd amd64 && make vagrant-windows-rust-amd64.box"
$ sh -c "cd i386 && make vagrant-windows-rust-i386.box"
```

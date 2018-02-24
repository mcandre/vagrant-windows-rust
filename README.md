# vagrant-windows-rust: a Vagrant box for building Rust binaries for Windows

# VAGRANT CLOUD

https://app.vagrantup.com/mcandre/boxes/vagrant-windows-rust

# EXAMPLE

```console
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
$ make vagrant-windows-rust.box
```

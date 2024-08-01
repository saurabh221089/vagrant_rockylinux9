# vagrant_rockylinux9
This repo is for creating a Vagrant box for RockyLinux9 in VirtualBox using Vagrant tool

```
$ vagrant init rockylinux/9

$ vagrant validate
Vagrantfile validated successfully.

$ vagrant up

$ vagrant provision
==> default: Running provisioner: shell...
    default: Running: inline script
    default: Last metadata expiration check: 0:36:06 ago on Wed 26 Jun 2024 04:56:33 PM UTC.
    default: Dependencies resolved.
    default: Nothing to do.
    default: Complete!

$ vagrant ssh

$ vagrant package --output=rockylinux9.box
==> default: Attempting graceful shutdown of VM...
==> default: Clearing any previously set forwarded ports...
==> default: Exporting VM...
==> default: Compressing package to: /mnt/c/projects/vagrant-test/rockylinux9.box

$ vagrant destroy

$ vagrant global-status

$ vagrant global-status --prune

$ vagrant box list  (List all the Vagrant boxes & their versions downloaded on your local)

```
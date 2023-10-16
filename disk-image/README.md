Use the following to validate the boot json file:

```bash
    ./packer validate boot-exit/boot-exit.json
```

To build, use this:
```bash
    ./packer build boot-exit/boot-exit.json
```

Per several stack-overflow articles, the `qemu-system-x86_64` is no longer the nomenclature for getting `qemu` to run. Use one of the following to install qemu:

For Ubuntu
```bash
sudo apt install qemu-kvm virt-manager virtinst libvirt-clients bridge-utils libvirt-daemon-system -y
```

For Fedora
```bash
sudo yum install qemu-kvm virt-manager virtinst libvirt-clients bridge-utils libvirt-daemon-system -y
```
To start the kvm:
```bash
sudo systemctl enable --now libvirtd
sudo systemctl start libvirtd
```

May need some permissions
```bash
sudo usermod -aG kvm $USER
sudo usermod -aG libvirt $USER
```

To get gem5 to cooperate :
```bash
sudo ln -s /usr/libexec/qemu-kvm /usr/bin/qemu-kvm
sudo ln -s /usr/bin/qemu-kvm /usr/bin/qemu-system-x86_64
```

### Resize image
```
qemu-img resize noble-server-cloudimg-amd64.img 60GB
```

### Install qemu agent
```
sudo apt install libguestfs-tools
```

```
virt-customize -a noble-server-cloudimg-amd64.img --install qemu-guest-agent --truncate /etc/machine-id
```

### Create VM Template
```
qm create 9999 -name ubuntu-24.04LTS --core 1 --memory 1024 --net0 virtio,bridge=vmbr0
```

### Import disk image
```
qm disk import 9999 noble-server-cloudimg-amd64.img local-lvm
```

### Add storage image on VM
```
qm set 9999 --scsihw virtio-scsi-pci --scsi0 local-lvm:vm-9999-disk-0
```

### Set primary boot harddisk on VM
```
qm set 9999 --boot c --bootdisk scsi0
```

### Activation qemu agent
```
qm set 9999 --agent 1
```

### Add optional serial, vga, hotplug
```
qm set 9999 --serial0 socket
```
```
qm set 9999 --vga serial0
```
```
qm set 9999 --hotplug network,usb,disk
```

### Convert to template
```
qm template 9999
```

### Create API Token on Proxmox
Datacenter > API Token > Add > select user > fill Token ID > Uncheck Privilege Separation > click Add

Copy and Save Token ID and Secret


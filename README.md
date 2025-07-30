Packages to install
linux 
mkinitcpio-netconf
dhclient
linux-firmware
s3fs-fuse


Replace the /etc files with the above etc folder contents

```mkinitcpio -p linux```

```
qemu-system-x86_64 \
  -m 4G \
  -kernel /boot/vmlinuz-linux \
  -initrd /boot/initramfs-linux.img \
  -append "console=ttyS0 rd.break" \
  -netdev user,id=network0 \
  -device e1000,netdev=network0 \
  -bios /usr/share/OVMF/x64/OVMF.4m.fd \
  -nographic \
  -serial mon:stdio
```


To check if fuse is working  
```ls -l /dev/fuse```  
crw-rw-rw-    1 0        0          10, 229 Jul 22 11:35 /dev/fuse  

```fusermount --version```  
fusermount version: 2.9.9  

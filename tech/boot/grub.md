# GRUB

## Install into UEFI Partition

Say, for an `x86_64` ubuntu installation:

- Boot into a live linux environment
- Mount the system EFI parition to, say, `/mnt/EFI`
- Mount the root fs of the installation to boot into to, say `/mnt/linux-root`

Install GRUB: 

```bash
grub-install \
    --target=x86_64-efi \
    --efi-directory=/mnt/EFI \
    --bootloader-id=ubuntu \
    --boot-directory=/mnt/linux-root/boot
```

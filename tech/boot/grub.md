# GRUB

## Install into UEFI Partition

Say, for an `x86_64` ubuntu installation:

- Boot into a live linux environment
- Mount the system EFI parition to, say, `/mnt/EFI`
- Mount the root fs of the installation to boot into to, say `/mnt/linux-root`

Install GRUB: 

```bash
EFI_DEV="/dev/sda1"
ROOT_DEV="/dev/sda2"
ROOT_MNT="/mnt/root"
GRUB_TARGET=x86_64-efi

sudo mkdir $ROOT_MNT
sudo mount $ROOT_DEV $ROOT_MNT
sudo mount $EFI_DEV $ROOT_MNT/boot/efi

sudo grub-install \
    --target=$GRUB_TARGET \
    --efi-directory=$ROOT_MNT/boot/efi/EFI \
    --bootloader-id=ubuntu \
    --boot-directory=$ROOT_MNT/boot
    --directory=$ROOT_MNT/usr/lib/grub/$GRUB_TARGET
```

### Alternative solution (That works on both UEFI and BIOS)

- Chroot in, mount essentials for operation, grub-install as usual.

```bash
EFI_DEV="/dev/sda1"
ROOT_DEV="/dev/sda2"
ROOT_MNT="/mnt/root"

sudo mkdir $ROOT_MNT
sudo mount $ROOT_DEV $ROOT_MNT
sudo mount $EFI_DEV $ROOT_MNT/boot/efi

for i in /dev /dev/pts /proc /sys /run; do sudo mount -B $i $ROOT_MNT/$i; done
sudo chroot $ROOT_MNT
grub-install $EFI_DEV
update-grub
exit
```

---

Tip: If reinstall grub on a different setup, make sure boot mounts in `/etc/fstab` with
filesystem UUIDs are adjusted accordingly.
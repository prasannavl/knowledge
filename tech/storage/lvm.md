# LVM

## Terminology

### PV — Physical Volume
The the first thing LVM needs is a physical storage device. This can be an entire disk, a partition or even a file (loopback).

### VG — Volume Group
Physical volumes are organized in volume groups, forming something like virtual disks and allowing multiple, separate physical storage devices to be viewed by the system as one large, contiguous device. There’s usually no need to have more than one VG, except if we want different allocation policies or extent sizes.

### LV — Logical Volume
A virtual logical partition that resides in a volume group. These will host our filesystems.

### PE — Physical Extent
Information is divided in equal parts (blocks) of data. This is how LVM keeps track of where data is stored (mapped from the virtual volume, to the real devices). An 8MB file might have 4MB stored on physical volume /dev/vdb and 4MB on /dev/vdc. These are two extents.

## Install

`sudo apt install lvm2`

## Usage

Cmd | Notes
--- | --- 
`lvmdiskscan` | Full scan
`pvs`, `vgs`, `lvs` | Scan
`pvcreate </dev/device>` | Create PV
`vgcreate <group_name> </dev/device ..>` | Create VG
`lvcreate --extents 100%VG --name <volume_name> <group_name>` | Create LV

## Size Options

`100%FREE`, `50%FREE`, `10G`, `20M`, `2T`, etc
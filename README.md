# Crucial MX500 Firmwares
Repository will only affect Linux installation. Please note that firmware is suitable for all form factors.

## Difference versions

Version M3CR033:

This firmware will update the MX500 SSD from version M3CR032 to M3CR033. If your SSD has version any version besides M3CR032, this firmware update is not applicable and not necessary. M3CR033 includes the following changes:

    Fixed SATA protocol error that causes start-up failure on certain data center RAID systems
    Improved boot time after unexpected power loss
    Fixed Read DMA command abort after an interrupted Secure Erase

Version M3CR023:

    This firmware will update the MX500 SSD to version M3CR023.

## Install on Linux

 1. [Download the firmware](https://www.crucial.com/support/ssd-support/mx500-support) or from this repository
 2. Extract the startup ramdisk from the ISO:

```bash
cd empty-folder
mount -o loop MX500_M3CR023_update.iso /mnt/iso
gzip -dc /mnt/iso/boot/corepure64.gz | cpio -idm
```
 3. Run the files from the current folder:

```bash
./sbin/msecli -L
./sbin/msecli -U -v -i ./opt/firmware/ -n /dev/sda # choose the correct drive
```

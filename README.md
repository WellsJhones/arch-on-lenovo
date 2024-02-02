# arch-on-lenovo
install arch without problem dualboot <br>
replace /** */ with the name of your ssd/hd driver

commands <br>
 lsblk <br>
 list the disk and partitions <br><br>
 cfdisk /dev/** */ <br>
 use this to modify the partitions use <br>
 for EFI use 600mb type EFI System <br>
 for swap use 2gb type Linux swap <br>
 for the system use whatever you want type Linux filesystem <br>
 select write partitions and exit<br><br>
lsblk to check the partitions<br>
# format partition UFI
mkfs.vfat -F 32 /dev/** */
# format partition swap
mkswap /dev/** */
# format partition for file system
mkfs.ext4 /dev/** */



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
# creat a directory
mkdir /mnt/archinstall <br>
# mount partition file system
mount /dev/** */  /mnt/archintall
# creat a folder 
mkdir /mnt/archinstall/boot
# mont partition EFI/boot
mount /dev/** */ /mnt/archinstall/boot
# config swap
swapon /dev/** */
# call the script archinstall
disk configuration select Pre-mounted configuration<br>
bootloader select systemd-boot default <br>
add user and root password with sudo previleges<br>
profile Desktop<br>
network configuration use NetworkManager <br>
optional repositories multilib<br>
and finaly install
# copy filesto boot on windows
mkdir /mnt/"name your windows"<br>
lsblk check the partition with 100mb <br>
mount /dev/** */ <br>
mount /dev/** */ /mnt/"your windows name"<br>
cd /mnt/"your windows name" <br>
cd EFI <br>
cp -r /mnt/"your windows name"/EFI/Microsoft /boot/EFI <br>






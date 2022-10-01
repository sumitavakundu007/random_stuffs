# random_stuffs
Few random commands for linux/Windows

# 1. External Hard-disk realted
## (i) Desktop
### Find the external hard disk path through terminal
```bash
df -h
```
### Find your hard disk. Let's say the path is /media/sdc/HardDisk. 
### To give the read, write permission,
```bash
sudo chmod -R a+rwX /media/sdc/HardDisk
```
### Unmount the device through terminal
```bash
sudo umount /media/sdc/HardDisk
```
## (ii) Cluster (CentOS)
```bash
sudo fdisk -l
sudo mkdir /usb
sudo mount /dev/sdc1 /usb
sudo mount | grep sdc1
sudo df -h
cd /usb
```
### To unmount teh device form cluster
```bash
fuser -cuk /mnt
sudo umount /dev/sdX
```

## References
1. https://askubuntu.com/questions/527304/how-to-change-permission-of-a-drive-in-an-external-hard-disik
2. https://linuxhint.com/mount-usb-drive-centos/:~:text=According%20to%20the%20%E2%80%9Cfdisk%E2%80%9D%20command,hard%20drives%20or%20USB%20drives.
3. https://unix.stackexchange.com/questions/19918/umount-device-is-busy


# 2. 'rsync' related command
### rsync command and flags
```bash
rsync -av --progress --max-size=1g --exclude={'dir3/*', 'file1.txt', 'dir1'} /src /dest
```
# 3. Check file and floder size
### Check file size
```bash
ls -lsrh
```
### Folder size
```bash
du -sh -- *
```
# 4. 'ffmpeg' related
```bash
ffmpeg -r 2 -i input_file_%02d.png -s 1920x957 -vframes 1000 -b 4800000 -r 2 output_file.mp4
```
Change the frame rates accordingly

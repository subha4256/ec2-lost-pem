# ec2-lost-pem


    - lsblk -f
     Create tempvolume for mounting
    - sudo mkdir /mnt/tempvol
     Mount tempvolume [below one is for xfs filesystem]
    - sudo mount -t xfs -o nouuid /dev/xvdf1 /mnt/tempvol
     Check Mounting
    - lsblk -f
     copy authorized_keys to mounted volume
    - cp .ssh/authorized_keys /mnt/tempvol/home/ec2-user/.ssh/
     Check the content on new volume
    - ls -lah /mnt/tempvol/home/ec2-user/.ssh/
     umount the secondary volume
    - sudo umount /mnt/tempvol



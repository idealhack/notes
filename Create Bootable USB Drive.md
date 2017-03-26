# Create Bootable USB Drive


## macOS

    # commands selected from [How to Create a Bootable Ubuntu USB Drive, for Mac, in OS X](https://business.tutsplus.com/tutorials/how-to-create-a-bootable-ubuntu-usb-drive-for-mac-in-os-x--cms-21253) 
    hdiutil convert -format UDRW -o system.img system.iso
    diskutil list
    diskutil unmountDisk /dev/disk2
    sudo dd if=system.img.dmg of=/dev/rdisk2 bs=1m
    # wait about 4 mins
    diskutil eject /dev/disk2

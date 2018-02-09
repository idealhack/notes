# System Installation

## Create Bootable USB Drive

### macOS

#### dd

[How to Create a Bootable Ubuntu USB Drive, for Mac, in OS X](https://business.tutsplus.com/tutorials/how-to-create-a-bootable-ubuntu-usb-drive-for-mac-in-os-x--cms-21253)

    hdiutil convert -format UDRW -o system.img system.iso
    diskutil list
    diskutil unmountDisk /dev/disk2
    sudo dd if=system.img.dmg of=/dev/rdisk2 bs=1m
    # wait about 4 mins
    diskutil eject /dev/disk2

#### [UNetbootin](https://unetbootin.github.io/)

#### [深度启动盘制作工具](https://www.deepin.org/original/deepin-boot-maker/)

### Linux / Windows

#### [Rufus - 轻松创建USB启动盘](http://rufus.akeo.ie/?locale=zh_CN)

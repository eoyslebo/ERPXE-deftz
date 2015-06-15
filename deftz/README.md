deft
========

Plugin for https://github.com/ERPXE/tftpboot

```bash
export ISODIR=/tftpboot/tmp
export ERPXEDIR=/tftpboot
mkdir -p $ISODIR
cd $ISODIR
wget http://na.mirror.garr.it/mirrors/deft/deftZ-rc1.iso
cd $ERPXEDIR/er/plugins
git clone https://github.com/eoyslebo/ERPXE-deftz
mv ERPXE-deftz deftz
mount $ISODIR/deftZ-rc1.iso /cdrom
cp /cdrom/preseed/lubuntu.seed $ERPXEDIR/er/plugins/deftz/lubuntu.seed
cp /cdrom/isolinux/splash.png $ERPXEDIR/er/plugins/deftz/deftz.png
cp /cdrom/casper/vmlinuz $ERPXEDIR/er/plugins/deftz/vmlinuz
cp /cdrom/casper/initrd.lz $ERPXEDIR/er/plugins/deftz/initrd.lz
mkdir -p $ERPXEDIR/er/shares/deftz/casper/
cp /cdrom/casper/filesystem.squashfs $ERPXEDIR/er/shares/deftz/casper/
umount /cdrom
$ERPXEDIR/bin/replace_nfsroot_ip.sh
```

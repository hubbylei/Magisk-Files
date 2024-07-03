## Magisk (300b233a) (27003)
- Simplify MediaStoreUtils
- Update docs to cover riscv64
- Add riscv64 support
- Add option to disable filename randomization
- Catch PendingIntent.CanceledException caused by send()<br><br>Accidentally changed in 050a073.
- check empty init_boot partition<br><br>For upgrading devices that continue to use Android 12 or older kernel versions, the generic ramdisk remains where it was with no requirement for a new init_boot image.

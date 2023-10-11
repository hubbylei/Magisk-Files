## Magisk (187f583c) (26301)
- Fix $RECOVERYMODE from config being incorrectly overridden<br><br>Move legacy SAR checking logic into mount_partitions, and avoid calling get_flags before check_boot_ramdisk<br>Fix #7346
- Update ONDK to r26.1
- AVD test release builds as well

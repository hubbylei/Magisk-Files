## Magisk (2aba7247) (28103)
- Skip stub APK install on emulator<br><br>Reduce test flakiness
- API 36 does not support wait_for_bootanim
- avd_test: upgrade to android16 beta3
- native: delete global 16k option<br><br>NDK 28 enable 16 KiB page size compatibility option by default, delete the global option to restore 4k alignment for 32-bit arch.
- app: target sdk 36

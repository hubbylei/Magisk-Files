## Magisk (a657af5d) (30600)
- Refine useLocaleManager with intent check for locales<br><br>This fixes https://github.com/topjohnwu/Magisk/issues/9628.
- chore: Update outdated GitHub Actions versions
- support sony's init.real
- Fix A-only addon.d retaining PREINITDEVICE on 30300+<br><br>- broken after https://github.com/topjohnwu/Magisk/commit/742913ebcb10cf819a54699497359535047874f7 so use get_flags to be more futureproof
- Add nativeSpecializeAppProcess signature for XR devices running 14<br><br>Build fingerprint: google/gms_sdk_xr64_x86_64/emulator64_x86_64:14/UP1A.231005.007.A1/13953962:userdebug/test-keys
- Fix formatting and update comments in bootimg.cpp
- magiskboot: Fix tail offset calculation
- Fix magiskboot cpio ls -r

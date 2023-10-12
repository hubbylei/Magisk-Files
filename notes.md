## Magisk (b0b04690) (26301)
- Use newer bash version for avd_test.sh
- Cleaner cstr code
- Borrow value instead of moving in FsPath::from()<br><br>When accepting a value of AsRef<Utf8CStr> in FsPath::from(), the<br>existing code will move a value of Utf8CStrBufArr, creating a reference<br>that lives longer than the borrowing value, causing undefined behavior.<br><br>The issue is only visible on release builds, as more advanced<br>optimizations will be more aggressive re-using the stack of variables<br>that no longer lives.<br><br>Fix #7408
- Update avd_test.sh
- Allow AVD hacks on release builds

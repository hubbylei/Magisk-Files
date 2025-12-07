## Magisk (0936cdb1) (30600)
- Update nativeForkAndSpecialize signature for A16 QPR2<br><br>https://android.googlesource.com/platform/frameworks/base.git/+/67a4b1b2fee385f798d75ad02d016b80fc79f075
- Enable CI for API 36.1
- Disable Zygisk upon incomplete JNI hook<br><br>Do not enable Zygisk unless ALL replacements are hooked properly.<br>This allow Zygisk tests to fail when new signature is introduced.

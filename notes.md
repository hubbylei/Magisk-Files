## Magisk (61ea59a2) (26402)
- API 34 AOSP ATD image is released
- Update Portuguese Translation
- Update Portuguese Translation
- Update dependencies
- Update selinux to disable validation for policydb
- Make tmpfs mount of magic mount atomic<br><br>This avoid system libraries disappear temporarily during magic mount,<br>which causes some dynamic executables fails to run during post-fs-data.
- Fix zygiskd not restart when zygote restarts

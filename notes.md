## Magisk (e73ff679) (28101)
- scripts: flash_script.sh: Avoid overly dangerous code
- Perform authentication if needed for AutomaticResponse setting
- Support systemlessly deleting files or folders<br><br>After we refactor the magic mount and always mount folder as tmpfs,<br>we can easily support deleting files or folders now. We recognize<br>dummy devices with major number 0 and minor number 0 as an indicator<br>for removing files and folders. This indicator is borrowed from<br>overlayfs.
- Allow kernel to relabel
- Use rust to implement collect/reset overlay context
- init: reset overlay.d files context after sepolicy loaded
- Revert \Allow all domains to access tmpfs files\<br><br>This reverts commit da43ac89a07c7b13b4cf4ae1539c95363ecd1f9f.
- Use /metadata/watchdog as preinit dir if exists<br><br>Since Android 15, all domains are allowed to search /metadata so preinit<br>dir will be exposed. Use /metadata/watchdog when /metadata is chosen as<br>preinit device, and the dir is available (since Android 11).

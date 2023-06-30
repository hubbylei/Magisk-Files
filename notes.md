## Magisk (46770db1) (26103)
- Rename stuffs
- Fix close
- Fix file permission
- Fix mmap block device
- Skip magisk32 for 64bit only avd
- Standardize logging and error handling<br><br>- Introduce new types: LoggedResult and LoggedError<br>- Introduce new extension methods to log and add additional msgs<br>- Never exit when logging error messages in Rust (all errors should be<br> handled by using Result and Rust's error propagation)<br>- Remove all usages of anyhow as it doesn't fit Magisk's use cases

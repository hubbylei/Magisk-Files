## Magisk (6ff82c4e) (28102)
- Introduce FsPathFollow<br><br>Make sure all operations of FsPath do not follow symlinks, and provide<br>a way to explicitly switch over to a set of operations that DO follow<br>symlinks by FsPath::follow_link.
- Move magiskpolicy cli to argh
- Update release script
- Replace zlib with zlib-rs
- Upgrade argh to stable release
- Migration to Edition 2024
- Update Cargo.toml

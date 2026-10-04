# Magisk (5381a1e9) (31000-40)

> Remove legacy apk codebase<br>Remove the legacy view-based APK module (:apk-legacy), along with its<br>subcommands, configurations, release packaging steps, and associated<br>unused dependencies.<br>Assisted-by: Gemini 3.8 Flash

> magiskboot: detect format for XZ BCJ filter<br>Detect the architecture and file format from input bytes to apply the<br>proper BCJ pre-filter when compressing with XZ:<br>- ELF binaries: map e_machine to x86, ARM-Thumb, ARM64, or RISC-V.<br>- Linux kernels: detect ARM64 raw Image, RISC-V Image, and ARM32 raw<br> vmlinux.bin via condition-code density.<br>- Non-code data: omit BCJ filters to avoid degradation.<br>Introduce get_encoder_bcj_detection and eliminate the redundant<br>compress_bytes_kernel and compress_len_kernel helpers.<br>Assisted-by: Gemini 3.8 Flash

> Allow 30 seconds for app migration in tests<br>The hidden app compiles its dynamic APK on first launch. On API 24<br>this pushes package removal past the 20-second receiver timeout.<br>Wait up to 30 seconds while still requiring the removal broadcast.<br>Assisted-by: GPT-6

> sepolicy: switch to open_memstream<br>Replace BSD funopen with POSIX open_memstream when dumping the policy<br>image into memory. Also update the crt0 submodule which implements<br>open_memstream and fixes duplicate mmap64 definitions on 32-bit targets.<br>Assisted-by: Gemini 3.8 Flash

> Fix host build compatibility with GCC<br>Fix compilation errors when building host binaries (such as magiskboot)<br>using GCC on Linux:<br>- Define _GNU_SOURCE in base and boot build.rs for glibc extensions.<br>- Add missing <cstdarg>, <cstring>, and <memory> standard headers.<br>- Provide a fallback definition for __printflike on glibc.<br>- Implement portable strscpy without relying on BSD strlcpy.<br>- Add unwrap_ref in bootimg.hpp to allow binding references to packed<br> struct members under GCC.<br>- Remove cxx_impl_annotations in codegen.rs to prevent always_inline<br> from being emitted on header declarations without function bodies.<br>Assisted-by: Gemini 3.8 Flash

> magiskboot: support building on host<br>Allow magiskboot to be built directly on host platforms (macOS and<br>Linux) using Cargo:<br>- Add a binary target to boot module with a no_main entry point that<br> directly reuses the C main CLI implementation.<br>- Compile native C and C++ sources (base, boot, cxx, and lz4) via cc in<br> base and boot build.rs when target_os is not Android.<br>- Platform gate Linux-specific functionality (SELinux xattrs, mount,<br> namespaces) in base on Linux and Android, and provide macOS fallback<br> for xsendfile.<br>- Move MountInfo and mount parsing from files to mount module.<br>- Scope Android-specific LTO rustflags in config.toml to Android<br> targets.<br>- Ensure build.py compiles Rust modules as static libraries (--lib).<br>Assisted-by: Gemini 3.8 Flash

> Expose xpipe2 as symbol

> Cleanup base.cpp

> base: eliminate /proc/self/fd path resolution<br>Remove reliance on /proc/self/fd symlink resolution across base and core<br>components:<br>- Add top-level pre_order_walk and post_order_walk that track entry<br> paths via an internal buffer, and unify Directory walk methods to<br> support path-tracking and pathless traversals without extra overhead.<br>- Add DirEntry::get_stat using fstatat(AT_SYMLINK_NOFOLLOW) directly on<br> directory file descriptors.<br>- Update Directory::copy_into and link_into to operate directly on file<br> descriptors with fd_get_attr/fd_set_attr, passing paths only for<br> symlink attribute updates.<br>- Refactor find_apk_path and restore_tmpcon to use pre_order_walk, and<br> update get_app_no_list to use DirEntry::get_stat.<br>- Remove DirEntry::resolve_path, Directory::path_at,<br> Directory::resolve_path, and fd_path.<br>- Replace remaining consumers of xrealpath and canonical_path (in su<br> and magiskinit) with standard realpath or partition matching, allowing<br> removal of Utf8CStr::realpath and its C FFI exports.<br>Assisted-by: Gemini 3.8 Flash

> Reduce more Linux specific code in base

> Move daemon utilities from base to core<br>Move utilities that are exclusively used by the daemon (core module)<br>from base to core:<br>- fork_dont_care, fork_no_orphan, new_daemon_thread, init_argv0,<br> set_nice_name, and switch_mnt_ns into utils.cpp<br>- exec_command* functions and exec_t into scripting.cpp as static<br> functions, as scripting is their sole consumer<br>Also remove the unused exec_command_sync overload.<br>Assisted-by: Gemini 3.8 Flash

> Use nix Errno


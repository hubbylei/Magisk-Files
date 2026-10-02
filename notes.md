# Magisk (5b06d817) (31000-40)

> Fix stub theme

> Revert "Update AVB hash header image_size to match unpacked original_image_size."<br>This reverts commit d9a9b02c277f4a94545a1e23a7493d0c64a0066d.

> app: fix D-pad focus and navigation issues<br>Fix multiple D-pad focus traversal and containment defects reported on<br>Android TV and non-touch devices:<br>- Pager focus bleed: Set beyondViewportPageCount = 0 on HorizontalPager<br> in MainScreen and LogScreen. Constrain horizontal and upward focus<br> exits on pager page containers using focusProperties and focusGroup so<br> DPAD_RIGHT on module cards or switches does not oscillate into<br> adjacent offscreen tabs.<br>- LogScreen focus leak: Wrap log tabs in focus boundaries to prevent<br> DPAD_UP at the top of the logs from escaping into the Home tab.<br>- Module install accessibility: Wire bidirectional D-pad focus between<br> ShortNavigationBar (Modules tab), the root FloatingActionButton, and<br> the module card list using FocusRequesters. Remove redundant install<br> buttons from TopAppBar and EmptyState.<br>Fixes #10113<br>Assisted-by: Gemini 3.8 Flash

> Refactor adb patching and emulator setup<br>Add support for patching boot images directly via adb<br>with the build.py script.

> Update cargo dependencies

> magiskboot: enable BCJ filter for XZ compression<br>Enable the architecture-specific BCJ pre-filter when creating XzWriter<br>for supported ABIs. For ARM32 kernel compression, use the standard ARM<br>filter rather than Thumb-2.<br>Assisted-by: Gemini 3.8 Flash

> Update xz-embedded to upstream submodule<br>Add https://github.com/tukaani-project/xz-embedded as a submodule<br>pinned to tag v2024-12-30, replacing previously vendored sources.<br>Keep customized userspace configuration in external/xz_config with<br>architecture-specific BCJ filters and CRC64 support.<br>Assisted-by: Gemini 3.8 Flash

> Update gradle dependencies

> magiskboot: handle decompression errors in unpack<br>Previously, decompress_bytes dropped the LoggedResult from decoding,<br>returning void. In bootimg.cpp, unpack and split_image_dtb never checked<br>whether decompression succeeded, leaving empty 0-byte output files and<br>returning RETURN_OK (0).<br>Return a boolean status from decompress_bytes and check it during unpack<br>and split_image_dtb. On decompression failure, remove any incomplete<br>output files and return RETURN_ERROR (1).<br>Assisted-by: Gemini 3.8 Flash

> magiskboot: search compressed formats in zImage<br>When locating the compressed piggy payload in a zImage, check only<br>formats where fmt.is_compressed() to avoid false positives on container<br>or header formats (such as DTB or Android boot magic).<br>Additionally, prioritize 4-byte aligned offsets since ARM kernel linker<br>scripts align .piggydata to 4 bytes, falling back to an unaligned scan<br>only if no candidate is found.<br>Assisted-by: Gemini 3.8 Flash

> magiskboot: validate XZ header CRC in check_fmt<br>XZ decompressor stubs in 32-bit ARM Linux zImage (lib/decompress_unxz.c)<br>include the HEADER_MAGIC string literal "\\3757zXZ" in .rodata, which<br>appears before the compressed payload. check_fmt previously matched<br>only the first 5 bytes, falsely identifying the .rodata string literal<br>as an XZ payload.<br>Validate the 12-byte XZ stream header by verifying the 6-byte magic,<br>stream flags, and IEEE 802.3 CRC32 of the stream flags. In addition,<br>harden GZIP, BZIP2, and LZOP checks with stricter header validation<br>to prevent false positives when scanning raw binaries.<br>Assisted-by: Gemini 3.8 Flash

> app: fix scrollbar touch interception<br>Only consume pointer events when the scrollbar is visible and touch hits<br>the thumb, preventing edge touches from teleporting the scroll position<br>when the scrollbar is invisible.<br>In addition, compute drag fraction relative to the initial grab offset<br>within the thumb to prevent jump-on-grab.<br>Assisted-by: Gemini 3.8 Flash

> app: fix dialog scrolling and scrollbar layout<br>Resolve scrolling, touch interception, and scrollbar layout defects<br>in markdown dialogs across the apk module:<br>- Dialog: Implement LinkClickMovementMethod to handle link taps without<br> intercepting drag gestures, allowing Compose to retain momentum and<br> fling physics.<br>- Dialog: Rebuild MagiskDialog with Dialog and Surface to allow<br> scrollable content to extend to the card boundaries, positioning the<br> scrollbar at the outer edge while keeping text padding intact to<br> prevent overlap. Support neutralButton and scrollable parameters.<br>- HomeScreen & ModuleScreen: Use scrollable MagiskDialog for install<br> and module changelog dialogs.<br>Assisted-by: Gemini 3.8 Flash

> Enhance legalFilename function to handle control characters

> Fix su daemon exec behavior after rust migration<br>Use fork_dont_care() to perform async exec and unblock all signals.

> build: show progress when downloading ONDK<br>Wrap the HTTP response stream in setup_ndk with a ProgressStream reader<br>to display a dynamic terminal progress bar showing percentage and<br>transferred megabytes during download and decompression.<br>Updates are throttled to at most 10 Hz and suppressed in non-interactive<br>environments.<br>Assisted-by: Gemini 3.8 Flash

> build: improve build.py and env.py scripts<br>Modernize build scripts and improve reliability across environments:<br>- Update required Java toolchain to JDK 25 across scripts and CI<br>- Propagate subprocess exit codes and report filesystem errors<br>- Fix argument parsing edge cases and dynamic linker path handling<br>- Anchor working directory and improve terminal output formatting<br>Assisted-by: Gemini 3.8 Flash


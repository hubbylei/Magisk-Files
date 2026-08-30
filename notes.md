## Magisk (b2d86c79) (30700)
- Add webview zygote as umount target<br>https://github.com/tiann/KernelSU/commit/4521784328352c54334beb29e05c74360b60d7cb
- Fix legacy app launch
- Update links, icons, and developer
- Bump MIN_NON_EMPTY_DTB_SIZE to 0x84
- su: Enable logging and notify by default<br>When a UID makes a root request for the first time, no row exists in<br>the policies table. Previously, RootSettings derived Default, which<br>initialized log and notify to false. As a result, connect_app() skipped<br>calling app_log() or app_notify() immediately after user approval on<br>the initial su request.<br>Explicitly implement Default for RootSettings with log and notify set<br>to true by default.<br>Assisted-by: Gemini 3.7 Flash
- app-ng: center align empty state placeholder text<br>Set textAlign = TextAlign.Center on the empty state placeholder text in<br>SuperuserScreen and ModuleScreen so multi-line messages are centered<br>horizontally instead of left-aligned.<br>Assisted-by: Gemini 3.7 Flash
- app-ng: support horizontal scrolling in terminal<br>Increase the terminal buffer columns to prevent text lines from wrapping<br>at the screen boundary, and enable bidirectional scrolling in<br>TerminalScreen.<br>Track the maximum used column across terminal lines dynamically to<br>constrain horizontal scrolling to actual content, and add a horizontal<br>scrollbar component matching the vertical scrollbar.<br>Assisted-by: Gemini 3.7 Flash

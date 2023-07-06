## Magisk (606d97ae) (26103)
- Trace location from LoggedError<br><br>Co-authored-by: topjohnwu <topjohnwu@gmail.com>
- Custom help message when using argh<br><br>Help messages generated from argh is nearly useless and very hard to<br>customize. Fork argh and disable all code for generating help messages.<br><br>Use a closure to print the help message when handling EarlyExit.
- Handle cpio commands properly

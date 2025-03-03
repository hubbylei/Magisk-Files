## Magisk (c6c1a17a) (28102)
- Address several clippy warnings
- Also run clippy with release mode<br><br>[skip ci]
- Support zImage compression types other than gzip.<br><br>Instead of just searching for the gzip magic, it now incrementally searches the kernel for the first thing that `check_fmt_lg` doesn't report as `UNKNOWN`.
- Skip all tests on master push
- Fix cache save condition

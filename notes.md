## Magisk (3ba00858) (26302)
- Allow avd_magisk on API 28
- Fix fd sanitization
- Do not go through magiskd for getting the log pipe
- Remove unnecessary RefCell usage
- Make log pipe a FIFO instead of anonymous pipe
- Better logging in recv_fds
- Make tmpfs path static strings
- Simplify zygisk log pipe

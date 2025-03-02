## Magisk (8c3c7d01) (28102)
- Skip all tests on master push
- Fix cache save condition
- Build on master push
- Do not store cache on pull request
- Delete bootctl binary if execution fails<br><br>New devices may use AIDL bootctrl HAL, so if bootctl hal-info fails,\r<br>simply remove the temp file and return.

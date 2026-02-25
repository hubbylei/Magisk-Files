## Magisk (e8a58776) (30700)
- Release Magisk v30.7<br>[skip ci]
- Add CI tests for Android 17
- Update cargo dependencies
- Update app dependencies
- Add jni hooks signature for nubia
- Update to ONDK r29.5
- Update getModuleDir() API doc
- Update libsepol to upstream Android 16 QPR2
- Update ota.md<br>Hi there, appreciate you and your work.<br>Proposing a small change to the A/B device update instructions, based on your changes within the Magisk app which made those instructions outdated/ invalid. <br>Specifically, after installing Magisk to the new slot, apparently Magisk then instructs to go back to the system update and hit restart now, instead of the prior instructions which remain on this website of rebooting within the Magisk app. I just did testing, and rebooting within the Magisk app does not result in slot switch, which must be why you noe instruct to go back to system update for the restart now. <br>Just thought I'd update the instructions for anyone who might be confused. <br>Thx!

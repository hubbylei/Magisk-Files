## Magisk (be5ff681) (27003)
- Exclude apache commons codec resources
- Move manager.sh to app_functions.sh
- Prevent polluting global shell env
- Cleanup configs
- Update Simplified Chinese Translation<br><br>Signed-off-by: Li Hua <lihua@email.com>
- Update Portuguese translation
- Set default visibility of restart button to GONE<br><br>This fixes the issue that button still shows when installation fails.
- Unset FLAG_ACTIVITY_NO_HISTORY for SuRequestActivity<br><br>This fixes device credential confirm activity on OnePlus devices<br>because SuRequestActivity is accidentally finished before a valid<br>response is delivered to it.
- Fix StackOverflowError<br><br>Now field from base class java.io.ByteArrayOutputStream shadows the property with custom getter from derived class com.topjohnwu.magisk.core.utils.AXML.RawByteStream. This behavior will be changed soon in favor of the property. Please use explicit cast to java.io.ByteArrayOutputStream if you wish to preserve current behavior. See https://youtrack.jetbrains.com/issue/KT-55017 for details

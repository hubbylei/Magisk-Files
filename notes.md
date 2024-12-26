## Magisk (231a5d18) (28101)
- Cleanup test code
- Drive app migration tests through instrumentation<br><br>Make tests less flaky
- Test su request via instrumentation
- Install and test LSPosed through test app
- Redesign test APK architecture<br><br>The test APK and the main APK share the same process and classloader,<br>and in the non-hidden case, the test APK's classes take precedence over<br>the ones in the main APK. This causes issues because the test APK and<br>main APK share some dependencies, but don't always use the same<br>version. This is especially problematic for the Kotlin stdlib and<br>AndroidX dependencies.<br><br>The solution here is to rely on R8's obfuscation feature and repackage<br>all potentially conflicting classes into a separate package in the test<br>APK. To ensure that the test classes are always using the same classes<br>as the main APK, we have to directly implement all tests inside the main<br>APK, making the test APK purely a \test runner with test dependencies\.<br><br>As a result, the test APK can only be used when built in release mode,<br>because R8 no longer allow class obfuscation to be enabled when building<br>for debug versions.
- Add ability to skip certain test variants

## Magisk (ecb31eed) (26401)
- Prevent Zygisk from closing new fds created by Zygote itself
- Refactor hookJniNativeMethods<br><br>Utilize NativeBridgeRuntimeCallbacks we obtained from native bridge<br>to directly fetch and modify registered native JNI methods.<br>By doing so, we do not need to keep a copy of every single<br>JNINativeMethod registered in order to provide JNI hooking<br>functionality.<br><br>Co-authored-by: LoveSy <shana@zju.edu.cn>
- Obtain NativeBridgeRuntimeCallbacks for future use<br><br>NativeBridgeRuntimeCallbacks can be used for better JNI method hooking<br><br>Co-authored-by: topjohnwu <topjohnwu@gmail.com>
- Clean up codes
- Refactor zygisk to use native bridge to inject<br><br>Co-authored-by: vvb2060 <vvb2060@gmail.com><br>Co-authored-by: topjohnwu <topjohnwu@gmail.com>
- Inject zygisk.rc for sync `--zygisk-restart`

## Magisk (8c4341e9) (30700)
- Prepare for v31.0 release
- app: fix navigation when flashing modules<br>When launching a flash intent using FLAG_ACTIVITY_CLEAR_TOP, Android<br>recreates MainActivity if singleTop or singleTask is not set, causing<br>the app to briefly display the home screen before showing the flash<br>screen.<br>Set MainActivity to singleTask, add FLAG_ACTIVITY_SINGLE_TOP to flash<br>intents, and default cold-start flash zip intents to the modules tab.<br>Assisted-by: Gemini 3.7 Flash
- app-legacy: add webview zygote to denylist<br>Port WebView Zygote denylist support to the legacy app module.<br>Assisted-by: Gemini 3.7 Flash
- Promote next-gen app to production, and demote existing app to legacy

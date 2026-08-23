## Magisk (7600d366) (30700)
- app: default to Monet theme and filter pre-Android S<br>Default to Monet (dynamic color) theme options on supported API<br>versions (Android S+) while hiding Monet options on unsupported<br>versions (< Android S).<br>Introduce ColorMode enum to encapsulate theme modes and UI index<br>mapping logic cleanly.<br>Assisted-by: Gemini 3.6 Flash
- apk-ng: refine M3 theme color schemes<br>Update light and dark color schemes in apk-ng to strictly align with<br>Material 3 Expressive color guidelines. Explicitly define surface<br>container tokens for improved contrast and card visibility, and<br>enhance primary and tertiary accents.<br>Assisted-by: Gemini 3.6 Flash
- Update AGENTS.md

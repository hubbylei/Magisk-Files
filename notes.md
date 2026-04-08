## Magisk (2f4bb014) (30700)
- Update cargo dependencies
- Update gradle dependencies
- Add basic AGENTS.md for application code
- Move stub resources into its own module<br>Stop relying on internal AGP intermediate paths in the build directory.<br>Use standard AGP classes to achieve the same result
- Extract environment setup into its own script<br>This simplifies environment setup for shell operations
- Delete previously generated component classes in stub
- Cleanup PreferenceConfig
- Use tools:sdk-common for build-logic

# Magisk (1629d447) (31000-41)

> app: hide Superuser log tab without root access<br>Omit PrimaryTabRow and SuLogTab in LogScreen when Info.env.isActive is<br>false, rendering MagiskLogTab directly below TopAppBar and skipping<br>SuLog database queries in LogViewModel.<br>Assisted-by: Gemini 4 Argon

> app: fix truncated text in SuLogCard header<br>Replace the 3-column ListItem in SuLogCard with a Row and Column<br>layout that places the action badge alongside the app name and gives<br>the UID/PID and timestamp lines the full header width without single-<br>line truncation.<br>Assisted-by: Gemini 4 Argon


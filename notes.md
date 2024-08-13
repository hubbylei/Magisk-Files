## Magisk (5a554836) (27006)
- Set `-fno-threadsafe-statics` for crt0<br><br>Since crt0 has no pthread support, we don't need lock for statics.

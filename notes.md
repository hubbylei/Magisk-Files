## Magisk (8cab1299) (26403)
- Update strings.xml / German translation
- Prevent race condition in wait
- Use platform implementation if possible
- Slightly change wait usage and API
- Add `resetprop -w` for waiting property change<br><br>It's very easy to wait for property change both in Java and C++,<br>but it's not the case in shell script. With this patch, developers<br>can now easily to wait for property change, just like what we have<br>in `.rc` files, and to wait for boot complete.
- Keep mirror shared before magic mount<br><br>This allows mounting during post-fs-data be kept after magic mount
- Fix magisk --stop by making mirror shared<br><br>Previously mirror is private and then unshared to zygote, which<br>makes magisk --stop cannot propagate umount mirror to zygote.
- Hide magisk internal mount point

## Magisk (4dd6e3c2) (30600)
- Minor changes for app
- Optimize preinit finding and add klogdump partition<br>* Use major number check to filter out device-mapper devices while preserving virtio-blk compatibility.<br>* Introduce `klogdump` partition support for Smartisan devices as a valid preinit target.
- Allow reacquiring capabilities if not explicitly cleared<br><br>- Old behavior: Switching to a non-zero UID was implicitly interpreted as a request to drop capabilities, thereby preventing subsequent reacquisition via `su`.<br>- New behavior: Switching to a non-zero UID now requires the `--drop-cap` argument to explicitly prevent the reacquisition of capabilities.
- Reorder positional arguments in Backup and Remove

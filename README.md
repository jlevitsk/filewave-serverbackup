# filewave-serverbackup

The script that can backup and restore a FileWave Server. Download it, make it executable, then run it without arguments to see syntax.

## Temporary backup location

Version 4.5.5 no longer uses `/tmp` as the large temporary staging area for database/config archives. This matters on Debian 13, where `/tmp` is mounted as `tmpfs` by default and can consume memory.

Default temporary roots:

- Linux: `/var/tmp/filewave-serverbackup`
- macOS: `/private/var/tmp/filewave-serverbackup`

You can override the temporary root per run:

```bash
FW_BACKUP_TEMP_ROOT=/path/to/disk-backed-temp ./backup_server_osx_linux.sh run /path/to/backup manual
```

Or edit the `temp_root` variable near the top of the script. Use a local disk-backed path with enough free space for the FileWave database/config archive.

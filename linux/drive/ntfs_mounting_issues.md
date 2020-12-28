# NTFS Drive Mounting Issues

Due to _hibernation_ in Windows 10, the NTFS drive may **_not be in a clean state_**.

In Windows 10, while shutting down the system we are basically hybernating the system (this can be changed). Windows sets a flag which tells the other OS that windows is hibernating.

So other OSs might open the drive in Read-Only mode. This is done to avoid corruption of data.

```bash
$ sudo ntfsfix /dev/sdXY

$ sudo mount -o rw /dev/sdXY
# or
$ sudo mount -o rw /dev/partition /mounting/directory

# list mounted partitions, their location, type & mode
$ mount -v
```

----

### Links
1. [Cant Mount NTFS Drive - stackoverflow.com](https://askubuntu.com/questions/462381/cant-mount-ntfs-drive-the-disk-contains-an-unclean-file-system)
2. [Unable to mount windows NTFS filesystem due to hibernation - askubuntu.com](https://askubuntu.com/questions/145902/unable-to-mount-windows-ntfs-filesystem-due-to-hibernation)
3. [Remount a filesystem as Read/Write - askubuntu.com](https://askubuntu.com/questions/175739/how-do-i-remount-a-filesystem-as-read-write)

# Chane swap UUID in fstab

Linux must know the UUID of swap, which changes when you remake a partition. If you remake your swap partition after installing, Linux will be confused and take a long time to log in.

1. Get a list of your partitions:
`sudo blkid`

*Look at the list and find* TYPE="swap" *with* UUID="ab20cd31ef42-some-long-number"

2. Open a GUI editor with GUI password entry (copy-paste is easier with GUI)
`gksu gedit /etc/fstab`

*If you don't have* `gedit`*, you can use* `mousepad` (Xfce) *or* `kate` (KDE) *or* `pluma` (MATE/Cinnamon) * or whatever else instead*

Now, look at the /etc/fstab file that opened in the GUI. It has the swap UUID two times, the first was swap at install, usually "ext4" and not "swap". Later is the actual swap. Change the actual one.

Copy that long UUID number for swap from the terminal (Ctrl+Shift+C for terminal) and use that to replace the UUID swap number in /etc/fstab.

Save, close, relogin.

All is good and right in the world.
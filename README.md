# linux-troubleshooting

### How to fix busybox Initramfs Error on Ubuntu or Linux.
Ubuntu Linux <pre>Ubuntu 20.04 LTS</pre>. You can try in your new version.


(initramfs) exit

the root filesystem on /dev/sda1 requires a manual.

As you can see in the above output, the /dev/sda1 (your/partition/name) partition is corrupted. The file system in this partition has some errors. If you even encountered, you need to check and repair the problematic Linux filesystem with fsck command .

(initramfs) reboot

Now, type “reboot” and hit ENTER to restart your system!

if the reboot command doesn´t work, type exit and hit ENTER.

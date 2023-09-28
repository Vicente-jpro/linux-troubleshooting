# linux-troubleshooting

### How to fix busybox Initramfs Error on Ubuntu or Linux.
Ubuntu Linux `Ubuntu 20.04 LTS`. You can try using another version.

<pre>(initramfs) exit</pre>

the root filesystem on `/dev/sda1` requires a manual. <br/>

As you can see in the above output, the `/dev/sda1` (your/partition/name) partition is corrupted. The file system in this partition has some errors. If you even encountered, you need to check and repair the problematic Linux filesystem with `fsck` command. <br/>

<pre>(initramfs) reboot</pre>

Now, type `reboot` and hit `ENTER` to restart your system!

if the reboot command doesn´t work, type `exit` and hit `ENTER`.

### Hardware tips
Command to see the computer serial number.
```sh
sudo dmidecode -t system | grep Serial
```

### Things you shoud know affer change your processor:
- Processor model
- Matherboard
- Soquete
- Thermal Design Power(TDP) `warning: Your TDP(potence) have to be equal than your TDP processor`
  You are going to find your Processor model here in this website.
  <a href="https://www.cpu-upgrade.com/CPUs/Intel/Core_i5_Mobile/i5-4300U.html"> CPU Upgrate.<a/>

  ### Create installer usb
```sh
  sudo dd if=image_name.bin of=/dev/sdN bs=4M status=progress
```
`image_name.bin`: nome do arquivo do instalador salvo <br>
`/dev/sdN`: o drive USB



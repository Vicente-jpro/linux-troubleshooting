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

### Check my RAM memory in linux
```sh
sudo dmidecode --type 17
```

### Search file in linux
Run the command `sudo find / -name *.rdb` <br>
`.rdb` is file extension

```sh
sudo find / -name *.rdb
```


Creating environment variables on a Linux system can be done in several ways, depending on whether you want the variable to be temporary (for the current session) or persistent (across reboots and sessions). Here are the steps for both scenarios:

### Temporary Environment Variables

These variables are set for the current session and will be lost once the session ends.

1. **Set a temporary environment variable:**
   ```sh
   export VARIABLE_NAME=value
   ```
   Example:
   ```sh
   export MY_VAR="Hello World"
   ```

2. **Check if the variable is set:**
   ```sh
   echo $VARIABLE_NAME
   ```
   Example:
   ```sh
   echo $MY_VAR
   ```

### Persistent Environment Variables

These variables are set in configuration files and will persist across sessions and reboots.

1. **For all users (system-wide):**
   
   Edit the `/etc/environment` file. This file is used to set system-wide environment variables.

   ```sh
   sudo nano /etc/environment
   ```

   Add your variables in the following format:
   ```sh
   VARIABLE_NAME=value
   ```
   Example:
   ```sh
   MY_VAR="Hello World"
   ```

   After editing, save the file and exit the text editor.

2. **For a single user (session-specific):**

   Edit the user's shell configuration file. This can be `.bashrc`, `.bash_profile`, `.profile`, or `.zshrc` depending on the shell being used.

   For bash shell (`.bashrc` or `.bash_profile`):
   ```sh
   nano ~/.bashrc
   ```
   or
   ```sh
   nano ~/.bash_profile
   ```

   For zsh shell (`.zshrc`):
   ```sh
   nano ~/.zshrc
   ```

   Add your variables at the end of the file:
   ```sh
   export VARIABLE_NAME=value
   ```
   Example:
   ```sh
   export MY_VAR="Hello World"
   ```

   After editing, save the file and exit the text editor.

3. **Apply the changes:**

   After editing the file, you need to reload the shell configuration file to apply the changes. This can be done by running:

   ```sh
   source ~/.bashrc
   ```
   or
   ```sh
   source ~/.bash_profile
   ```
   or
   ```sh
   source ~/.zshrc
   ```

### Verify the Environment Variable

To check if the environment variable is set correctly, you can use the `echo` command:

```sh
echo $VARIABLE_NAME
```
Example:
```sh
echo $MY_VAR
```

This will print the value of `MY_VAR` if it is set correctly.

### Summary

- **Temporary variables:** Use `export VARIABLE_NAME=value` in the terminal.
- **Persistent variables (system-wide):** Add `VARIABLE_NAME=value` to `/etc/environment`.
- **Persistent variables (single user):** Add `export VARIABLE_NAME=value` to `~/.bashrc`, `~/.bash_profile`, `~/.profile`, or `~/.zshrc`.

Reload the configuration files using `source` to apply the changes.

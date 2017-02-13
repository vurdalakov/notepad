# Useful Ubuntu commands

Scope: `Ubuntu 16`+

#### Get Ubuntu version

```
lsb_release -a
```

```
vurdalakov@workstation:~$ lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 16.04.1 LTS
Release:        16.04
Codename:       xenial
```

#### Get Ubuntu installation time

```
ls -al /var/log/installer/syslog
```

#### Get last Ubuntu boot time

```
who -b
```

#### Determine if Ubuntu is 32-bit or 64-bit

```
uname -i
```

Result for 32-bit is `i686` and for 64-bit is `x86_64`.

```
file /lib/systemd/systemd
```

Output for 32-bit contains ` ELF 32-bit` and for 64-bit is `ELF 64-bit`.

#### Determine Ubuntu endianness

```
echo I | tr -d [:space:] | od -to2 | head -n1 | awk '{print $2}' | cut -c6
```

Result is `1` for little endian and `0` for big endian.

```
lscpu | grep -i endian
```

Result is `Little Endian` or `Big Endian`.

#### Reboot Ubuntu

```
systemctl reboot
```

Ignore other logged in users and restart:

```
sudo systemctl reboot -i
```

#### Shutdown Ubuntu

```
systemctl poweroff
```

Ignore other logged in users and shutdown:

```
sudo systemctl poweroff -i
```

#### Get list of installed packages

```
apt list --installed
```

#### Find if specific package is installed

```
apt list --installed | grep packagename
```

#### Simple text editor

```
nano filename
```

#### Create file

```
touch filename
```

#### Make file executable

```
sudo chmod +x filename
```

#### Create directory if not exists

```
mkdir -p /tmp/logs
```

#### Run command in background

```
ls &
```

#### Switch to root user

```
sudo su
```

#### List USB devices

```
lsusb
```

#### Rescan SCSI disks

```
for i in /sys/class/scsi_host/*; do echo $i; echo "- - -" > sudo $i/scan; done
```

Or

```
sudo apt-get install scsitools
```

```
sudo rescan-scsi-bus
```

#### Enumerate X displays

```
w -hs | awk '{print $3}' | sort -u
```

#### Make screenshot from command line

```
gnome-screenshot --display=:0 --file=screenshot.png
```

#### Find process ID

```
pgrep processName
```

#### Kill process by ID

```
kill processID
```

#### Kill process by name

```
kill $(pgrep processName)
```

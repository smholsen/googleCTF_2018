# Moar

## Description
Finding yourself on the Foobanizer9000, a computer built by 9000 foos, this computer is so complicated luckily it serves manual pages through a network service. As the old saying goes, everything you need is in the manual.

$nc moar.ctfcompetition.com 1337
## Solution
The netcat from the description takes us to a manual of the utility *socat*. While within a man in Linux, we can still run shell commands by prepending a "!" to our commands. 
Looking in home/moar reveals a shellcode program with some interesting content.

```
$ nc moar.ctfcompetition.com 1337
socat(1)                                                              socat(1)

NAME
       socat - Multipurpose relay (SOcket CAT)

SYNOPSIS
       socat [options] <address> <address>
       socat -V
       socat -h[h[h]] | -?[?[?]]
       filan
       procan

DESCRIPTION
       Socat  is  a  command  line based utility that establishes two bidirec-
       tional byte streams  and  transfers  data  between  them.  Because  the
       streams  can be constructed from a large set of different types of data
       sinks and sources (see address types),  and  because  lots  of  address
       options  may be applied to the streams, socat can be used for many dif-
       ferent purposes.

       Filan is a utility  that  prints  information  about  its  active  file
       descriptors  to  stdout.  It  has been written for debugging socat, but
       might be useful for other purposes too. Use the -h option to find  more
 Manual page socat(1) line 1 (press h for help or q to quit)

!ls
bin   dev  home  lib64	mnt  proc  run	 srv  tmp  var
boot  etc  lib	 media	opt  root  sbin  sys  usr
!done  (press RETURN)

!ls home
moar
!done  (press RETURN)!ls home/moar

!ls home/moar
disable_dmz.sh
!done  (press RETURN)!cat home/moar/disable_dmz.sh

!cat home/moar/disable_dmz.sh
#!/bin/sh
echo 'Disabling DMZ using password CTF{...}'
echo CTF{...} > /dev/dmz
!done  (press RETURN)
```

## Useful Resources
[Shebang](https://en.wikipedia.org/wiki/Shebang_(Unix))

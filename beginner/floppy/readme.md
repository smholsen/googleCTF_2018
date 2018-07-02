# Floppy

## Description
Using the credentials from the letter, you logged in to the Foobanizer9000-PC. It has a floppy drive...why? There is an .ico file on the disk, but it doesn't smell right..

## Solution

After unzipping the attachement we obtain a .ico file, and running 
```
$ file foo.ico 
```
Outputs 
```
foo.ico: MS Windows icon resource - 1 icon, 32x32, 16 colors
```
Hmm...

Taking a closer look using any text editor reveals something that might look like a .txt file. Maybe it could be an archive?
Using binwalk reveals te following;
```
$ binwalk foo.ico 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
765           0x2FD           Zip archive data, at least v2.0 to extract, compressed size: 123, uncompressed size: 136, name: driver.txt
956           0x3BC           Zip archive data, at least v2.0 to extract, compressed size: 214, uncompressed size: 225, name: www.com
1392          0x570           End of Zip archive


```
So, there is a zip archive in there. 

Unzip again and get the flag from driver.txt.
```
$ cp foo.ico foo.zip

$ unzip foo.zip 
Archive:  foo.zip
warning [foo.zip]:  765 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: driver.txt              
  inflating: www.com                 

$ cat driver.txt 
This is the driver for the Aluminum-Key Hardware password storage device.
     CTF{...}

In case of emergency, run www.com

```


## Useful Resources
[binwalk](https://github.com/ReFirmLabs/binwalk/wiki)

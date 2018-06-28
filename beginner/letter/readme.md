# Letter

## Description
You really went dumpster diving? Amazing. After many hours, SUCCESS! Between what looks like a three week old casserole and a copy of "Relative-Time Magazine", you found this important looking letter about the victims PC. However the credentials aren't readable - can you still obtain them?

## Solution
Simply unzip the file, open it in a PDF viewer, and copy the password which is "blacked out".
```
$ ls
- 5a0fad5699f75dee39434cc26587411b948e0574a545ef4157e5bf4700e9d62a.zip

$ unzip 5a0fad5699f75dee39434cc26587411b948e0574a545ef4157e5bf4700e9d62a.zip 
Archive:  5a0fad5699f75dee39434cc26587411b948e0574a545ef4157e5bf4700e9d62a.zip
 extracting: challenge.pdf           

$ xdg-open challenge.pdf
```

## Useful Resources
[unzip](https://linux.die.net/man/1/unzip)
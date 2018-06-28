# OCR is Cool

## Description
Caesar once said, don't stab me… but taking a screenshot of an image sure feels like being stabbed. You connected to a VNC server on the Foobanizer 9000, it was view only. This screenshot is all that was present but it's gibberish. Can you recover the original text?

## Solution

After unzipping the attachement we obtain a screenshot of a gmail in a .png format. Upon viewing the content we can see a wall of gibberish text. 

Before running any OCR you should cut the image using e.g. gimp, so that your new image only contains the text from the mail.
You can now run OCR on the image using any tool you'd like. I experimented with tesseract, but there are also many online services that can help you. e.g. [this one](https://onlineocr.net/).
After running the OCR you should now be stuck with the following text:

```
Wxtk Vnlmhfxk.
Px tkx atiir mh pxevhfx tl hnk gxpxlm vnlmhfxk hy hnk lxvnkx bWkhiWkbox vehnw ybex latkbgz lxkobvx. T ltyx ietvx yhk tee rhnk ybexl.
 
Lmhkx tgr ybex
bWkhiWkbox lmtkml rhn pbma 15 IU hy ykxx hgebgx hk hyyebgx lmhktzx, lh rhn vtg dxxi ptkxs, ubgtkbxl, itbgmbgzl, yetzl. ybkfptkxl. ubmvhbgl, pkbmxnil — tgrmabgz.
 
Lxx rhnk lmnyy tgrpaxkx
Rhnk ybexl bg bWkhiWkbox vtg ux kxtvaxw ykhf tgr yhhutgbsxk, lftkm ykbwzx 2000, lftkm atnl, Mxfih-t-ftmbv, hk fxwbt iv. Lh paxkxoxk rhn zh, rhnk ybexl yheehp.
 
Latkx ybexl tgw yhewxkl
Rhn vtg jnbvder bgobmx hmaxkl mh obxp, whpgehtw, tgw vheetuhktmx hg tee max ybexl rhn ptgm obt xftbe tmmtvafxgml. Cnlm zbox maxf max ebgd VMY{vtxltkvbiaxkbltlnulmbmnmbhgvbiaxk} tgw maxr vtg tvvxll tee rhnk wtmt.
 
Yhk xqtfiex, axkx'l t eblm hy ybexl matm rhn'kx vnkkxgmer lmhkbgz pbma nl:
hyyanu_ybkfptkx.ubg ChagMK
BHM_vkxwxgmbtel.iwy\ 5(wxexmxw1) Pbgmxkfnmxw
Yhhutgbsxk9000_Ftgnte.iwy Pbgmxkfnmxw
yhh.bvh Mnkuh
 
Lbgvx px mtdx lxvnkbmr oxkr lxkbhnler tgw bg hkwxk mh ikhmxvm rhn tztbglm onegxktubebmbxl ebdx xytbe tgw tfwyetpl. px'kx lxgwbgz rhn rhnk vkxwxgmbtel nlbgz max mbfx-ikhoxg fbebmtkr-zktwx vtxltk lrffxmkbv vbiaxk.
 
Atiir bWkhiWkbobgz!
```

We can note the substring "VMY{vtxltkvbiaxkbltlnulmbmnmbhgvbiaxk}" as familiar. 

From the description text we also get some hints as to what cipher is in use. (Caecar once said ...).
We can use [this](http://theblob.org/rot.cgi) online service to see all 25 possible rotations at once. 

We now see that ROT-7 gives us an english text containing the following;

```
Dear Customer. We are happy to welcome as our newest customer of our secure iDropDrive cloud file sharing service. A safe place for all your files. Store any file iDropDrive starts you with 15 PB of free online or offline storage, so you can keep warez, binaries, paintings, flags. firmwares. bitcoins, writeups — anything. See your stuff anywhere Your files in iDropDrive can be reached from any foobanizer, smart fridge 2000, smart haus, Tempo-a-matic, or media pc. So wherever you go, your files follow. Share files and folders You can quickly invite others to view, download, and collaborate on all the files you want via email attachments. Just give them the link CTF{...} and they can access all your data. For example, here's a list of files that you're currently storing with us: offhub_firmware.bin JohnTR IOT_credentials.pdf\ 5(deleted1) Wintermuted Foobanizer9000_Manual.pdf Wintermuted foo.ico Turbo Since we take security very seriously and in order to protect you against vulnerabilities like efail and amdflaws. we're sending you your credentials using the time-proven military-grade caesar symmetric cipher. Happy iDropDriving!
```

## Useful Resources
[Tesseract](https://github.com/tesseract-ocr/)
[Online OCR](https://onlineocr.net/)
[Gimp](https://www.gimp.org/)
[ROT-N](http://theblob.org/rot.cgi) 
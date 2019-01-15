---
title: "Ubuntu Cosmic Print Hangup"
date: 2019-01-10T15:31:10-06:00
draft: false
---

This afternoon I had to sign some documents. They were provided
through DocuSign, which is nice but I'd rather have a hard copy for my
files. While trying to print these documents I had an issue with the
printer configuration on Ubuntu 18.10.

When I'd click through the printer configuration wizard it would open
a window with the error: `"Processing - Unable to locate printer"`. I
dug around a bit and `dmesg` showed that AppArmour was blocking cupsd.

I was in a hurry so the fastest answer I could think of was to tell
AppArmour to back off while I printed. Then to reactivate it afterwards.

``` bash
sudo aa-complain cupsd
```

Add the printer and print the records.

``` bash
sudo aa-enforce cupsd
```

This is explained, with a slightly different methodology, on the Ubuntu [wiki](https://wiki.ubuntu.com/DebuggingPrintingProblems#AppArmor_Protection_of_the_printing_system)

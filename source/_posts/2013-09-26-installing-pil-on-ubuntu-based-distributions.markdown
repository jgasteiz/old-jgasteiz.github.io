---
layout: post
title: "Installing PIL on Ubuntu based distributions"
date: 2013-09-26 21:09
comments: true
categories: Programming
---

Today I've been trying to run [grunt-glue](https://npmjs.org/package/grunt-glue) in my Elementary OS and after trying to understand why it wasn't running, I realised the JPEG/ZLIB support weren't working.

It usually happens when you install PIL via pip. To fix the issue, do the following:

Uninstall PIL from your virtualenv - please, use [virtualenv](https://pypi.python.org/pypi/virtualenv).

```
pip uninstall PIL
```

Install PIL dependencies - and python-dev, if you don't have it installed.

```
sudo apt-get build-dep python-imaging
sudo apt-get install python-dev
```

Create a few symbolic links and install PIL again. When you install PIL, do it with a -U argument to see some output of the installation. I've noticed the sources for 32bit installations would change to _i386-linux-gnu_ instead of _x86_64linux-gnu_.

```
sudo ln -s /usr/lib/x86_64-linux-gnu/libjpeg.so /usr/lib
sudo ln -s /usr/lib/x86_64-linux-gnu/libfreetype.so /usr/lib
sudo ln -s /usr/lib/x86_64-linux-gnu/libz.so /usr/lib

pip install -U PIL
```
If everything went fine, you shoould see something like this if you scroll up a bit:

```
--------------------------------------------------------------------
PIL 1.1.7 SETUP SUMMARY
--------------------------------------------------------------------
version       1.1.7
platform      linux2 2.7.3 (default, Apr 10 2013, 06:20:15)
              [GCC 4.6.3]
--------------------------------------------------------------------
*** TKINTER support not available
--- JPEG support available
--- ZLIB (PNG/ZIP) support available
--- FREETYPE2 support available
*** LITTLECMS support not available
--------------------------------------------------------------------
```

Another option, instead of creating those links manually, would be installing PIL in the machine python installation.

```
sudo apt-get install python-imaging
```

And another option, although not what you were looking for, would be installing Pillow - which is a better PIL, basically.

```
pip install Pillow
```

After any of these 3 options you should be able to use the python imaging library happily now.

PS: Thanks everyone for the corrections and suggestions for this post ;)
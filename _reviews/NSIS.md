---
layout: review
title: Nullsoft Scriptable Install System (NSIS)
url: https://nsis.sourceforge.io/
Cost: Free (zlib/libpng)
rating: 3
tags: software windows installer package developer build
---
Packaging for easy deployment is often my least favorate task to deal with. The tools are either super easy to use with next to no capabilities or super complicated with the ability to do almost anything you can think of. NSIS is neither simple or excessively complex. It is unfortanately still a text/code based packager but the scripting can be done in a fairly simple way. On the plus side it easier than WIX and can be hooked into your build process so that once its designed your good to go. 

<!--more-->

NSIS has a significant number of plugins that can simplify your life however they tend to be maintained as needed by the writers which can be problematic. I ended up writing my own plugin to handle [.Net Version Dependancy](https://vshed.us/NSIS_DotNetVersion/) checking. It also resulted in me developing a [String Explode](https://vshed.us/NSIS_strExplode/) plugin because the existing one worked backward to what makes since for version numbers. Other build realted tools for dealing with Embeded Lists and extracting binary details can be found on my [github](https://github.com/fatalwall?tab=repositories).

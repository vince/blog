---
layout: post
title:  "Getting a touchscreen events working with Firefox"
date:   2019-01-29 16:00:00 +0530
categories: blog
author:     vince
image:      /images/posts/linux-image.jpg
tags:
 - linux
 - firefox
---

```
tl;dr
-----
* modify .desktop file to add env MOZ_USE_XINPUT2=1
* alternatively launch Firefox from the command line with MOZ_USE_XINPUT2=1
```

I bought this laptop with a touchscreen and occasionally find myself using it while surfing websites. Now with Chrome that worked just fine but with Firefox it tends to select areas of text instead of scrolling. That sucks!

Fortunately it's quite fixable. You just have to modify the .desktop file (or launch from the command line) with an additional environmental option: `env MOZ_USE_XINPUT2=1`

On most linux distributions, the .desktop file is in .local/share/applications but you can also modify it globally in /usr/share/applications if you have root.

    vim ~/.local/share/applications/firefoxtouch.desktop

Then modify the Exec line so it looks like this instead:

```Exec=env MOZ_USE_XINPUT2=1 /usr/bin/firefox %u```

When you relaunch Firefox, you should have the ability to use your touchscreen in the same way Chrome uses it. Hopefully Firefox makes this the default in the future but as of version 65, I'm still waiting.
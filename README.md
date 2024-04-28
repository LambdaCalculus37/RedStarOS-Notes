# Notes and Findings about Red Star OS
This repository contains information about my findings and notes from talks I
have given about Red Star OS, the North Korean Linux distribution.

## What is Red Star OS?
Red Star OS is the infamous Linux distro developed in North Korea by the
[Korea Computer Center](https://en.wikipedia.org/wiki/Korea_Computer_Center).
In development since 1998, the OS was initially released in 2008 with version 1.0,
with a version 2.0 released in 2009, and followed by version 3.0 in 2012. Version
4.0 of Red Star was released in either 2019 or 2020, depending on sources cited, but
a DVD ISO image has yet to be leaked. My talk and most information on Red Star OS in
the wild is taken from version 3.0.

![The main desktop view of Red Star OS 3.0](/images/fresh_install.png)

On the surface, Red Star OS may appear to resemble macOS to quite a degree, but under
the hood, it's very much a Linux distro, albeit one that breaks quite a few conventions
of what most people think of when they think of Linux. I hope to outline as many of these
oddities and standouts in this article.

### Under the Hood

![results of uname -a in Red Star 3.0](/images/rs30-uname.png)

Red Star OS 3.0 appears to be derived from the Fedora Linux distro, roughly corresponding
to Fedora 15. There's no 64-bit version of the distro; only a 32-bit version was released.
As shown in the output for the 'uname -a' command, Red Star 3.0 uses the 2.6.38.8 release
of the Linux kernel, and some other hints to its Fedora roots are the use of .rpm packages
and the yum tool included; indeed, generic .rpm packages can be installed to Red Star OS,
and theoretically, Fedora .rpm packages could be coaxed into installing as well.

However, the real points of interest are in what Red Star OS is doing differently from
other Linux distros. Normally we would think of Linux as being a "free as in freedom"
operating system, with the source code for the system's components released under a
license that allows others to view and study the source to see how it works, but in
Red Star's case, being from such an oppresive, isolationist nation as North Korea
means that the source code is not going to be for outside prying eyes, so I guess
we won't be able too...

![Found the source for the kernel never mind](/images/rs30-kernel-source.png)

Wait never mind the kernel source code is included as an optional installable
package! We'll come back to this later!
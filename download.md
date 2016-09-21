---
layout: page
title: Download
permalink: /download/
---

The signature of each file should be checked against our GPG key which is available on the [contact](/contact) page.



## Virtual machines

Virtual machines are convenient for testing the project without installing it on bare metal. Don’t forget to enable nested virtualization and EPT.


### VMware

 * [cappsule - vmware.tar.xz](https://irma.quarkslab.com/cappsule/cappsule - vmware.tar.xz) (1.8Gb)
 * [cappsule - vmware.tar.xz.sig](https://irma.quarkslab.com/cappsule/cappsule - vmware.tar.xz.sig)
 * sha256sum: `338e8bbc71fb908111716cc694d81eb45f0641db9e4ad9d87e784312dc65d238`
 * Option: *Virtualize Intel VT-x/EPT or AMD-V/RVI*


### VirtualBox

 * [cappsule - virtualbox.tar.bz2](https://irma.quarkslab.com/cappsule/cappsule - virtualbox.tar.bz2) (2.2Gb)
 * [cappsule - virtualbox.tar.bz2.sig](https://irma.quarkslab.com/cappsule/cappsule - virtualbox.tar.bz2.sig)
 * sha256sum: `55c4995aaf1beb8918e20a3d9d64214f67ee1057d927b35370d682b82e2cd498`
 * *Enable VT-x/AMD-V* and *Enable Nested Paging*


### VM configuration

`user`'s password is `user`. Please note that an OpenSSH server is listening, but only public key authentication is supported for security reasons. Feel free to change this setting in `/etc/ssh/sshd_config` (`PermitPassword` option), or write your public key in `~/.ssh/authorized_keys`.



## Ubuntu packages

**Ubuntu 16 is the only distribution supported.** It may work without major modifications on other recent distributions. DISCLAIMER: The software is provided "as is" without warranty of any kind. It may kill your cat, wipe your hard drive, etc.

 * [cappsule-1.0.deb](https://irma.quarkslab.com/cappsule/cappsule-1.0.deb)
 * [cappsule-1.0.deb.sig](https://irma.quarkslab.com/cappsule/cappsule-1.0.deb.sig)
 * sha256sum: `ad2dea90da96f5653a54dff506dd82de14922e154ec1e6c5c7cfa02181613d90`

A server version without GUI support is available:

 * [cappsule-server-1.0.deb](https://irma.quarkslab.com/cappsule/cappsule-server-1.0.deb)
 * [cappsule-server-1.0.deb.sig](https://irma.quarkslab.com/cappsule/cappsule-server-1.0.deb.sig)
 * sha256sum: `b533eb613f588a816af603840c636f98afa04d8cbc38e893fabf8aaec7341d1f`


### GUI support

The GUI support is tricky to get right because it requires a specific setup. `Xorg` must be launched through `X-wrapper-qubes` without root privileges. Colorful borders are only available with a [patched](https://github.com/cappsule/userland/tree/master/devices/gui/metacity) version of `metacity`.

Nevertheless, Cappsule can be run without GUI support thanks to the server version, or using the following command lines:

 * `/usr/local/cappsule/usr/bin/daemon --no-gui`
 * `virt exec --no-gui`: launches cappsule without GUI



## Source code

Cappsule is under GPL. The source code is available on [GitHub](https://github.com/cappsule).

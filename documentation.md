---
layout: page
title: Documentation
permalink: /documentation/
---

## Full documentation

The full documentation is available in the [doc repository](https://github.com/cappsule/cappsule-doc/), and html files can be generated with the following commands:

    git clone https://github.com/cappsule/cappsule-doc.git doc
    make -C doc/ html



## Quick start

Get the sources:

    mkdir src/
    git clone https://github.com/cappsule/cappsule-hypervisor.git src/hv
    git clone https://github.com/cappsule/cappsule-userland.git src/userland
    git clone https://github.com/cappsule/cappsule-gui.git src/userland/devices/gui
    git clone https://github.com/cappsule/cappsule-tools.git tools

Build:

    make -C src/hv
    make -C src/userland

Install:

    ./tools/build_package.py -f ./cappsule.deb
    sudo dpkg --force-confnew -i ./cappsule.deb

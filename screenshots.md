---
layout: page
title: Screenshots
permalink: /screenshots/
---

## Desktop usage

A typical desktop usage for Cappsule: Firefox, gnome-terminal and evince, all launched inside 3 different VMs. The VMs are created instantly when the user clicks on the icons. Sounds familiar? It's because we use Qubes OS' [GUI protocol](https://www.qubes-os.org/doc/gui/). An example is worth thousands words, click the video below to see it in action (it can be played fullscreen with the button in the bottom right corner.)

<video id="cappsule-desktop-video" src="/data/cappsule-desktop.webm" controls width="100%" class="img-thumbnail center-block"></video>



## Kernel exploit

If a kernel vulnerability is found, its exploitation will have no impact on the host. The first execution of `getroot` will indeed give root privileges, however, the second time will crash the cappsule’s kernel. The cappsule is eventually killed because it tries to access to the hardware through an I/O.

<div id="player-container-1" class="center-block"></div>



## Random package

Let's take a common task: installing `vim` package (e.g. via `apt`). In Cappsule, everything is isolated from each other by default; the host filesystem remains unmodified but the package is still available and installed into the cappsule. Those changes are also persistent, you will not loose it when relaunching the cappsule.

<div id="player-container-2" class="center-block"></div>

<script>
  var video = document.getElementById("cappsule-desktop-video");
  if (window.location.href.search("autoplay") >= 0 && video.paused) {
    video.play();
  }
  asciinema.player.js.CreatePlayer('player-container-1', '/data/asciicast-43938.json', { width: 80, height: 24 });
  asciinema.player.js.CreatePlayer('player-container-2', '/data/asciicast-43950.json', { width: 80, height: 24 });
</script>

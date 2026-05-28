---
layout: default
title: Kindle Development
weight: 3
---

# Kindle Development
As mentioned in [Kindle OS](/kindle-os/), the Kindle runs Linux, this means that you can develop your own applications for it, which run natively on the Kindle.

This section of the wiki is primarily aimed towards native development with C/C++ via the Meson Build System

## Modifying Rootfs
Since `hdnext` all Kindle jailbreaks have been "rootless", this means that the rootfs, mounted on `/` **CANNOT** be modified, attempting to do so may cause bricks on older devices and **WILL** cause bricks on newer models (as `5.19` introduces `dm-verity` on certain models)

### KPM
The recommended method of modifying the rootfs is by utilising [KPM overlays](./kpm/overlays.html)
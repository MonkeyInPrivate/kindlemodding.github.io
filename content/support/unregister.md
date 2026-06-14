---
layout: default
parent: Other Guides
title: Preserving Files on Deregister
weight: 8
---

# Preserving files on Deregister

<p class="tip">Even after following this guide, your files/books may not appear on your homescreen after deregistering. Rest assured, your files have not been deleted. In order to fix this, simply backup the files to your computer, delete them from your Kindle, and copy them back from your computer to your Kindle.</p>

By default, removing your Amazon account from your Kindle, known as "deregistering", will also completely wipe your Kindle. Thankfully, this is relatively easy to bypass by just setting a system flag.

## Using a Scriptlet
<p class="warning">The below file is hosted on an external website provided by a member of the KMC Support team.</p>

1. Download the Scriptlet [here](https://raw.githubusercontent.com/GreenCat-777/GC-WIKI/refs/heads/main/downloads/preserve.sh).
2. Move the file to the `documents` folder on your Kindle 
3. It should automatically appear on your homescreen as a book, if it doesn't, make sure you have [installed the Hotfix](../jailbreaking/post-jailbreak/setting-up-a-hotfix/).
4. Open it.
5. If a message pops up then you can now safely deregister.

## With a Command
1. Open kterm (or any command prompt connected to your Kindle)
2. Run the command ```touch /var/local/DONT_DELETE_CONTENT_ON_DEREGISTRATION```

## With a Computer
<p class="important">As a regular USB connection to the Kindle doesn't provide root access, you will need to use KOReader or an SSH client to move the file to the correct directory.</p>

1. Make a new file on your computer called `DONT_DELETE_CONTENT_ON_DEREGISTRATION` **with no file extension/content**.
2. Move the file to your Kindle.
3. Using some method, move the file to `/var/local/`.
4. Confirm that the path looks like `/var/local/DONT_DELETE_CONTENT_ON_DEREGISTRATION`.

# Credits
[MonkeyInPrivate](https://github.com/MonkeyInPrivite) - Wrote this page
[GreenCat777](https://github.com/GreenCat-777) - Wrote and hosted the Scriptlet

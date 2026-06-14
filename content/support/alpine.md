---
layout: default
parent: Other Guides
title: Installing Alpine Linux
weight: 9
---

# Installing Alpine Linux

<p class="caution">While extremely rare, at least one case of this tool bricking a Kindle has been reported. If you end up in this situation, you should be able to recover by using the <a href="./repair/">Repair Guide</a>. But in any case, be careful and back up any important data!</p>

Surprisingly, running Alpine Linux on the Kindle is not only possible, but not very difficult.

## With a Scriptlet
<p class="tip">
Also available on <a href="./kforge">KindleForge</a>!</p>

1. Click [here](https://github.com/GreenCat-777/QuickAlpine/releases/latest/download/install_alpine.sh) to download the latest release.
2. Move the file to the `documents` folder on your Kindle 
3. It should automatically appear on your homescreen as a book, if it doesn't, make sure you have [installed the Hotfix](../jailbreaking/post-jailbreak/setting-up-a-hotfix/).
4. Open it.

## With KUAL
<p class="note">If you're experienced enough, you can modify this extension to run other versions of Alpine.</p>

1. Download the latest release [here](https://github.com/schuhumi/alpine_kindle_kual/releases/latest/download/alpine_kindle_kual.zip)
2. Extract the .zip file's contents to the `extensions` folder on your Kindle.
3. Start KUAL and open the newly made Alpine section.
4. Click the `Deploy` option to download the latest release from GitHub.

## Through KTerm
<p class="important">You can also do this through an SSH client.</p>
<p class="warning">The below link/script is externally managed by a member of the KMC Support team.</p>

1. Open [kterm](https://github.com/bfabiszewski/kterm)
2. Enter and run this command: ```sh -c "$(curl -fsSL https://tinyurl.com/alpinek)"```

## Credits
- [MonkeyInPrivate](https://github.com/MonkeyInPrivite) - Wrote this Page 
- [schuhumi](https://github.com/schuhumi) - Wrote Alpine for Kindle and the KUAL Installer
- [GreenCat777](https://github.com/GreenCat-777) - Wrote QuickAlpine(including the kterm link/script), and parts of this page

---
layout: default
title: Creating a Package
weight: 0
---

# Creating a Package
A KPM package can be created using the [`kpm-helper.py`](https://github.com/KindleModding/KPM/blob/main/kpm-helper.py) script:
```sh
# Step 1. Create a folder to store your package contents
mkdir example_package
# Step 2. Initialise the package folder
python kpm-helper.py package init ./example_package
```

The `example_package` folder will now look like this:
```sh
example_package
└── manifest.json

1 directory, 1 file
```

The manifest file will now be initialised to target the `kindleany` platform (see: [`targeting specific platforms`](./targeting-platforms.html))

## Hooks
You can now put any other files in the package folder, however they won't do anything by themselves, this is why we have hooks:

```sh
example_package
├── install.sh
├── launch.sh
├── manifest.json
└── uninstall.sh

1 directory, 4 files
```

| File Name    | Purpose                                                 |
|--------------|---------------------------------------------------------|
| install.sh   | Ran during package installation after it is unpacked    |
| uninstall.sh | Ran during package uninstallation after it is unmounted |
| launch.sh    | Ran when package is launched from a launcher            |

<p class="warning">Hooks <b>MUST NOT</b> write to rootfs or remount it as rw, see below for more details</p>

Hooks are always ran from the package's folder whilst the package is in an unpacked state, this means you can reference local files with relative paths.

It is encouraged to use the `install.sh` hook to drop a scriptlet in the `/mnt/us/documents` folder when appropriate.

## Writing To Rootfs
Due to the rootless nature of `hdnext` jailbreaks and modern Kindle firmware, it is not possible to write to the rootfs directly. Luckily an alternative exists using `bind` mounts and `overlayfs`, this is implemented by the `hdnext` system.

Anything you want to be written to `rootfs` must be placed in a special folder in your package called `rootfs`, for example:

```sh
example_package
├── install.sh
├── launch.sh
├── manifest.json
├── rootfs
│   └── opt
│       └── amazon
│           └── ebook
│               └── lib
│                   └── json_simple-1.1.jar
└── uninstall.sh

6 directories, 5 files
```
In this case, the file at `/opt/amazon/ebook/lib/json_simple-1.1.jar` would be overwritten via overlayfs with the one from `example_package`

### Notes on rootfs and hooks
Rootfs overlay operations always happen **BEFORE** the install and uninstall hooks, that is to say when `install.sh` runs, the file is already overlaid, and when `uninstall.sh` runs, the file is already removed.

<p class="warning">Do not use package rootfs for paths under <code>/var</code> or <code>/mnt</code></p>
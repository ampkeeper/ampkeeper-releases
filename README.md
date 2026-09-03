# AmpKeeper firmware releases

This repository publishes the signed firmware for **AmpKeeper**, a small local device
that watches your solar and tells your EV charger, or your Tesla directly, how much
current to draw, so your car charges on excess sunshine instead of the grid.

Every release here is an official build, signed by AmpKeeper and verified by the device
before it will install.

There is no source code in this repository; it holds release artifacts only.

**[ampkeeper.com](https://ampkeeper.com) has everything about the product itself: what
AmpKeeper does, which inverters, wallboxes and cars it works with, setup guides, and the
waiting list.**

## You probably don't need to download anything

Your AmpKeeper updates itself. Open its web app and go to **Settings › About › Firmware
update**: the Online update card checks this repository, tells you what is available and
installs it for you. This page exists for the cases where that is not possible, such as a
device with no internet access, or one being updated by hand.

See [CHANGELOG.md](CHANGELOG.md) for what changed in each version.

## What's in a release

Each version is published as a GitHub Release tagged `vX.Y.Z`, with these files:

| File | What it is |
| --- | --- |
| `app-ampkeeper.afw` | The firmware update. This is the one to pick if you are updating by hand. |
| `app-ampkeeper-rescue.afw` | The rescue bundle: the main firmware, packaged for the recovery page to install when a device has fallen back to recovery. |
| `build-info.txt` | What went into the build: version, build time, toolchain versions, and the size and checksum of each image. |

A separate release tagged **`manifest`** holds one file, `versions.json`. That is the list
your AmpKeeper reads when it checks for an update; it is replaced each time a new version
is published, so it always describes the current release.

Versions tagged `-beta.N` are pre-releases. A device on the stable channel ignores them;
one on the beta channel will offer them.

## Signatures

Every image is signed with AmpKeeper's release key, and the device checks that signature
against a key built into its own firmware before writing anything. An unsigned or altered
image is refused, whether it arrives over the internet or is uploaded by hand over your
local network. The signature covers the version and the other details of the release, not
just the image, so a release cannot be re-labelled or rolled back to an older one behind
your back.

`build-info.txt` lists each image's SHA-256 if you want to check a download yourself.

## Help

Start at [ampkeeper.com](https://ampkeeper.com). Your AmpKeeper also carries its own user
guides. Open the web app and go to **Help**, which works with no internet connection.

For anything else, email [hello@ampkeeper.com](mailto:hello@ampkeeper.com).

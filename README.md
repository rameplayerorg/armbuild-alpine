# armbuild-alpine

Based on https://github.com/armbuild/alpine 

`rootfs.tar` is built with `build.sh` script from that repo.

## How to make new rootfs.tar

The easiest way to make new `rootfs.tar` is to have running Alpine system with target architecture.

#### Example for Alpine 3.7:

1. Create temp directory for the image: `mkdir /tmp/rootfs`

2. Download: `apk --repository http://dl-cdn.alpinelinux.org/alpine/v3.7/main --update-cache --allow-untrusted --root /tmp/rootfs --initdb add alpine-base`

3. Add repository file: `echo "http://dl-cdn.alpinelinux.org/alpine/v3.7/main" > /tmp/rootfs/etc/apk/repositories`

4. Write image file: `tar --numeric-owner -C /tmp/rootfs -c . > rootfs.tar`

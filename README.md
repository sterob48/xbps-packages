## The XBPS source packages collection

This repository contains the XBPS source packages collection to build binary packages
for the Void Linux distribution.

To start using it first you'll need some external dependencies:

- bash
- fakeroot (only required by the bootstrap target)
- xbps >= 0.35

Make sure your user is added to the `xbuilder` group to be able to use `xbps-uchroot(8)`,
otherwise `xbps-src` won't work correctly.

The `xbps-src` utility will allow you to generate XBPS binary packages, type

     $ ./xbps-src -h

to see all available targets/options and start building any available package
in the `srcpkgs` directory.

The `etc/defaults.conf` file contains the possible settings that can be overrided
through the `etc/conf` configuration file for the `xbps-src` utility; optionally if
`~/.xbps-src.conf` exists it's also read after `etc/conf`.

If you want to customize default `CFLAGS`, `CXXFLAGS` and `LDFLAGS`, don't override
those defined in `etc/defaults.conf`, append to them instead via `etc/conf` i.e:

    $ echo 'XBPS_CFLAGS+=" your flags here "' >> etc/conf
    $ echo 'XBPS_LDFLAGS+=" your flags here "' >> etc/conf

See [Manual](https://github.com/voidlinux/xbps-packages/blob/master/Manual.md)
for documentation to create and learn about the source packages.

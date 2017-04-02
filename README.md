# alpine-pkg-nkf
This is a nkf (Network Kanji Filter) package for Alpine Linux.

## How to build a package
You can build a package by using the following commands.
This command generate a apk package for `nkf` and `nkf-doc` in `$PWD/packages`.
```
$ docker build nkf-builder .
$ docker run -v $PWD/packages:/packages -v ~/.abuild:/home/builder/.abuild:ro --rm nkf-builder
```

I assume that `~/.abuild` contains a private key file and `abuild.conf` (for several environment variables).
Here is an example:
```
PACKAGER_PRIVKEY="/home/builder/.abuild/private-key.rsa"
PACKAGER='Tomoya Tanjo <ttanjo@gmail.com>'
```

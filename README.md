# alpine-pkg-nlopt

[![CircleCI](https://img.shields.io/circleci/project/sgerrand/alpine-pkg-nlopt/master.svg)](https://circleci.com/gh/sgerrand/alpine-pkg-nlopt)

This is the [nlopt][nlopt] utility script as an Alpine Linux package.

## Releases

See the [releases page][releases] for the latest download links.

## Installing

The current installation method for these packages is to pull them in using
`wget` or `curl` and install the local file with the `--allow-untrusted` option
to `apk`:

```
apk --no-cache add ca-certificates
wget https://github.com/sgerrand/alpine-pkg-nlopt/releases/download/2.4.2-r0/nlopt-2.4.2-r0.apk
apk --allow-untrusted add nlopt-2.4.2-r0.apk
```

[nlopt]: http://ab-initio.mit.edu/wiki/index.php/NLopt
[releases]: https://github.com/sgerrand/alpine-pkg-nlopt/releases/

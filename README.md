[![Docker Stars](https://img.shields.io/docker/stars/dmreiland/alpine-oraclejdk10.svg?style=flat-square)](https://hub.docker.com/r/dmreiland/alpine-oraclejdk10/)
[![Docker Pulls](https://img.shields.io/docker/pulls/dmreiland/alpine-oraclejdk10.svg?style=flat-square)](https://hub.docker.com/r/dmreiland/alpine-oraclejdk10/)


OracleJDK 10 Docker image
========================

Thanks to [frovlad](https://github.com/frol/docker-alpine-oraclejdk8) and his excellent Java8 builds for providing a solid foundation.

This image is based on Alpine Linux image, which is only a 5MB image, and contains
[OracleJDK 10](http://www.oracle.com/technetwork/java/javase/overview/index.html).

You must accept the
[Oracle Binary Code License Agreement for Java SE](http://www.oracle.com/technetwork/java/javase/terms/license/index.html)
to use this image.

The JDK bundle contains lots of unnecessary for a Docker image, so it was cleaned up. There are 3
tags: `full` (only src tarballs get removed), `cleaned` (desktop parts get cleaned), `slim`
(everything but compiler and jvm is removed). `master` branch refers to `slim` tag, but `latest`
tag points to `cleaned`.

`slim` (`master` branch) download image size is:

[![](https://images.microbadger.com/badges/image/dmreiland/alpine-oraclejdk10:slim.svg)](http://microbadger.com/images/dmreiland/alpine-oraclejdk10:slim "Get your own image badge on microbadger.com")

`cleaned` (`latest` tag) download image size is:

[![](https://images.microbadger.com/badges/image/dmreiland/alpine-oraclejdk10:cleaned.svg)](http://microbadger.com/images/dmreiland/alpine-oraclejdk10:cleaned "Get your own image badge on microbadger.com")

`full` download image size is:

[![](https://images.microbadger.com/badges/image/dmreiland/alpine-oraclejdk10:full.svg)](http://microbadger.com/images/dmreiland/alpine-oraclejdk10:full "Get your own image badge on microbadger.com")


Consider using [`dmreiland/alpine-oraclejre10`](https://github.com/dmreiland/docker-alpine-oraclejre10)
image (~119MB) if you only need JRE (you can run Java applications, but cannot build/compile them).


Usage Example
-------------

```bash
$ echo 'public class Main { public static void main(String[] args) { System.out.println("Hello World"); } }' > Main.java
$ docker run --rm -v "$(pwd)":/mnt --workdir /mnt dmreiland/alpine-oraclejdk10:slim sh -c "javac Main.java && java Main"
```

Once you have run this command you will get printed 'Hello World' from Java!

# Pterodactyl Yolks

A curated collection of core images that can be used with Pterodactyl's Egg system. Each image is rebuilt
periodically (every month) to ensure dependencies are always up-to-date. This is a fork of the official yolks repo, but 
with major upgrades and different bases. 

Go, Node.js, and Python images use Debian 11 as the base, and uses `bash` instead of `ash`. Java 8 and 11 images are based on Ubuntu 20.04 ("Focal"), while Java 17, and 20 images are based on Ubuntu 22.04 ("Jammy"). All Java OpenJ9 images are based on Ubuntu 22.04, and all Java GraalVM images are based on Oracle Linux 9.

Images are hosted on `ghcr.io` and exist under the `games`, `installers`, and `yolks` spaces. The following logic
is used when determining which space an image will live under:

* `oses` — base images containing core packages to get you started.
* `games` — anything within the `games` folder in the repository. These are images built for running a specific game
or type of game. These have not been modified, and is up to date with Pterodactyl's official game yolks. It is recommended to use Pterodactyl's versions instead.
* `installers` — anything living within the `installers` directory. These images are used by install scripts for different
Eggs within Pterodactyl, not for actually running a game server. These images are only designed to reduce installation time
and network usage by pre-installing common installation dependencies such as `curl` and `wget`.
* `yolks` — these are more generic images that allow different types of games or scripts to run. They're generally just
a specific version of software and allow different Eggs within Pterodactyl to switch out the underlying implementation. An
example of this would be something like Java or Python which are used for running bots, Minecraft servers, etc.

All of these images are available for `linux/amd64` and `linux/arm64` versions, unless otherwise specified, to use
these images on an arm64 system, no modification to them or the tag is needed, they should just work.


## Contributing

When adding a new version to an existing image, such as `java v42`, you'd add it within a child folder of `java`, so
`java/42/Dockerfile` for example. Please also update the correct `.github/workflows` file to ensure that this new version
is tagged correctly.

## Available Images

* [`base oses`](https://github.com/No767/pt-yolks/tree/master/oses)
  * [`alpine`](https://github.com/No767/pt-yolks/tree/master/oses/alpine)
    * `ghcr.io/no767/pt-yolks:alpine`
  * [`debian`](https://github.com/No767/pt-yolks/tree/master/oses/debian)
    * `ghcr.io/no767/pt-yolks:debian`
* [`games`](https://github.com/pterodactyl/yolks/tree/master/games)
  * [`rust`](https://github.com/pterodactyl/yolks/tree/master/games/rust)
    * `ghcr.io/pterodactyl/games:rust`
  * [`source`](https://github.com/pterodactyl/yolks/tree/master/games/source)
    * `ghcr.io/pterodactyl/games:source`
* [`golang`](https://github.com/No767/pt-yolks/tree/master/go)
  * [`go1.19`](https://github.com/No767/pt-yolks/tree/master/go/1.19)
    * `ghcr.io/no767/pt-yolks:go_1.19`
  * [`go1.20`](https://github.com/No767/pt-yolks/tree/master/go/1.20)
    * `ghcr.io/no767/pt-yolks:go_1.20`
* [`java`](https://github.com/No767/pt-yolks/tree/master/java)
  * [`java8`](https://github.com/No767/pt-yolks/tree/master/java/8)
    * `ghcr.io/no767/pt-yolks:java_8`
  * [`java8 - OpenJ9`](https://github.com/No767/pt-yolks/tree/master/java/8j9)
    * `ghcr.io/no767/pt-yolks:java_8j9`
  * [`java8 - GraalVM`](https://github.com/No767/pt-yolks/tree/master/java/8graalvm)
    * `ghcr.io/no767/pt-yolks:java_8graalvm`
  * [`java11`](https://github.com/No767/pt-yolks/tree/master/java/11)
    * `ghcr.io/no767/pt-yolks:java_11`
  * [`java11 - OpenJ9`](https://github.com/No767/pt-yolks/tree/master/java/11j9)
    * `ghcr.io/no767/pt-yolks:java_11j9`
  * [`java11 - GraalVM`](https://github.com/No767/pt-yolks/tree/master/java/11graalvm)
    * `ghcr.io/no767/pt-yolks:java_11graalvm`
  * [`java17`](https://github.com/No767/pt-yolks/tree/master/java/17)
    * `ghcr.io/no767/pt-yolks:java_17`
  * [`java17 - OpenJ9`](https://github.com/No767/pt-yolks/tree/master/java/17j9)
    * `ghcr.io/no767/pt-yolks:java_17j9`
  * [`java17 - GraalVM`](https://github.com/No767/pt-yolks/tree/master/java/17graalvm)
    * `ghcr.io/no767/pt-yolks:java_17graalvm`
* [`nodejs`](https://github.com/No767/pt-yolks/tree/master/nodejs)
  * [`node18`](https://github.com/No767/pt-yolks/tree/master/nodejs/18)
    * `ghcr.io/no767/pt-yolks:nodejs_18`
  * [`node20`](https://github.com/No767/pt-yolks/tree/master/nodejs/20)
    * `ghcr.io/no767/pt-yolks:nodejs_20`
* [`python`](https://github.com/No767/pt-yolks/tree/master/python)
  * [`python3.8`](https://github.com/No767/pt-yolks/tree/master/python/3.8)
    * `ghcr.io/no767/pt-yolks:python_3.8`
  * [`python3.9`](https://github.com/No767/pt-yolks/tree/master/python/3.9)
    * `ghcr.io/no767/pt-yolks:python_3.9`
  * [`python3.10`](https://github.com/No767/pt-yolks/tree/master/python/3.10)
    * `ghcr.io/no767/pt-yolks:python_3.10`
  * [`python3.11`](https://github.com/No767/pt-yolks/tree/master/python/3.11)
    * `ghcr.io/no767/pt-yolks:python_3.11`

### Installation Images

* [`alpine-install`](https://github.com/no767/pt-yolks/tree/master/installers/alpine)
  * `ghcr.io/no767/pt-yolks:installer-alpine`

* [`debian-install`](https://github.com/no767/pt-yolks/tree/master/installers/debian)
  * `ghcr.io/no767/pt-yolks:installer-debian`

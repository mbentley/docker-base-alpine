# mbentley/alpine

These are docker images based off of official Alpine images on Docker Hub.

## Why

The images on Docker Hub are not always updated as regularly as I would like.  They can ship vulnerable libraries/binaries so in order to combat that, I am maintaining my own rebased images.  There are no customizations outside of patching and rebasing the images.

## Tags

The following is a list of multi-arch (`amd64`, `arm64`, `armv7`) tags for each release.

* __Hint__: You can also use the same rebased image tag with `-<arch>` appended (e.g. - `mbentley/alpine:latest-amd64`)

| Distro | Base Image | Rebased Image |
| ------ | ---------- | ------------- |
| Alpine | `alpine:latest`<br>`alpine:3.18` | `mbentley/alpine:latest`<br>`mbentley/alpine:3.18` |
| Alpine | `alpine:3.17` | `mbentley/alpine:3.17` |
| Alpine | `alpine:3.16` | `mbentley/alpine:3.16` |
| Alpine | `alpine:3.15` | `mbentley/alpine:3.15` |
| Alpine | `alpine:3.14` | `mbentley/alpine:3.14` |
| Alpine | `alpine:3.13` | `mbentley/alpine:3.13` |
| Alpine | `alpine:3.12` | `mbentley/alpine:3.12` |
| Alpine | `alpine:3.11` | `mbentley/alpine:3.11` |

## Re-Building the Images

### Alpine

``` bash
for VERSION in 3.18 3.17 3.16 3.15 3.14 3.13 3.12 3.11
do
  docker build --pull --build-arg IMAGE_TAG="${VERSION}" -t "mbentley/alpine:${VERSION}" -f Dockerfile.alpine .
done
```

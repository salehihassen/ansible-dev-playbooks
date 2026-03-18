# Docker install role

Based on https://docs.docker.com/engine/install/ubuntu/

Support installing Docker Engine on Ubuntu (or derivatives like PopOS) and Debian. 

The role writes a `deb822` apt source and pins the Docker repository to the host's Debian architecture
for example `amd64` or `arm64` so `apt update` does not attempt unsupported arches like `i386`.

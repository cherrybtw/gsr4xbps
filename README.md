# gsr4xbps

Unofficial [Void Linux](https://voidlinux.org) packages for [gpu-screen-recorder](https://git.dec05eba.com/gpu-screen-recorder/about) and its companions.

Packages are built for all Void Linux architectures: `x86_64`, `x86_64-musl`, `i686`, `aarch64`, `aarch64-musl`, `armv7l`, `armv7l-musl`, `armv6l`, `armv6l-musl`.

## Installing

<details>
<summary>Option 1 — Repository (recommended)</summary>

Add the signing key:

```sh
sudo xbps-fetch https://raw.githubusercontent.com/cherrybtw/gsr4xbps/main/pubkey.pem -o /var/db/xbps/keys/cherrybtw-gsr.pem
```

Add the repository:

```sh
echo 'repository=https://github.com/cherrybtw/gsr4xbps/releases/latest/download' | sudo tee /etc/xbps.d/0-gsr4xbps.conf
```

Install:

```sh
sudo xbps-install -Su gpu-screen-recorder-ui
```

`gpu-screen-recorder` and `gpu-screen-recorder-notification` will be pulled in as dependencies automatically.

> If you only need the CLI tool, install `gpu-screen-recorder` instead.

</details>

<details>
<summary>Option 2 — Build from template</summary>

Clone `void-packages` and bootstrap:

```sh
git clone https://github.com/void-linux/void-packages
cd void-packages
./xbps-src binary-bootstrap
```

Clone this repository and copy the packages into `void-packages/srcpkgs`:

```sh
git clone https://github.com/cherrybtw/gsr4xbps
cp -r gsr4xbps/srcpkgs/* void-packages/srcpkgs/
```

Build:

```sh
./xbps-src pkg gpu-screen-recorder-ui
```

Install:

```sh
sudo xbps-install -R hostdir/binpkgs gpu-screen-recorder-ui
```
> If you only need the CLI tool, build `gpu-screen-recorder` instead.

> If your `void-packages` or bootstrap is stale, update first:
> ```sh
> git -C void-packages pull origin master
> ./xbps-src bootstrap-update
> ```

</details>

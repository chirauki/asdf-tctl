# asdf-tctl

Shamelessly copied from [asdf-kubectl](https://github.com/asdf-community/asdf-kubectl).

tctl plugin for [asdf](https://github.com/asdf-vm/asdf) version manager.

## Install

```
asdf plugin-add tctl https://github.com/chirauki/asdf-tctl.git
```

## Use

Check out the [asdf documentation](https://asdf-vm.com/#/core-manage-versions?id=install-version) for instructions on how to install and manage versions of tctl.

## Architecture Override

The `ASDF_TCTL_OVERWRITE_ARCH` variable can be used to override the architecture that is used for determining which `tctl` build to download. The primary use case is when attempting to install an older version of `tctl` for use on an Apple M1 computer as `tctl` was not built for ARM at the time.

### Without `ASDF_TCTL_OVERWRITE_ARCH`:

```
$ asdf install tctl 1.5.2
Downloading tctl from https://binaries.dl.tetrate.io/public/raw/versions/darwin-amd64-1.5.2/tctl
```

### With `ASDF_TCTL_OVERWRITE_ARCH`:

```
$ ASDF_TCTL_OVERWRITE_ARCH=arm64 asdf install tctl 1.5.2
Downloading tctl from https://binaries.dl.tetrate.io/public/raw/versions/darwin-arm64-1.5.2/tctl
```

### Development version

If you have a custom build of `tctl` locally you can install a `dev` version targetting it (it will be linked to `asdf`'s bin folder). You need to specify the path to your custom binary using `ASDF_TCTL_DEV_PATH` env var.

```
$ ASDF_TCTL_DEV_PATH=/path/to/some/debug/bin/tctl asdf install tctl dev
```

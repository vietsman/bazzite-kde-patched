# bazzite-kde-patched &nbsp; [![bluebuild build badge](https://github.com/vietsman/bc250-patched-kernel/actions/workflows/build.yml/badge.svg)](https://github.com/vietsman/bc250-patched-kernel/actions/workflows/build.yml)

Bazzite KDE image for AMD BC-250 boards with patched kernel raising GPU max frequency to 2230 MHz (from 2000 MHz), lowering min GPU frequency to 350 MHz (from 1000 MHz), and oberon-governor included. 
## Installation

To rebase an existing Bazzite installation to this latest build:

- Rebase to the signed image, like so:
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/vietsman/bazzite-kde-patched:latest
  ```
- Reboot to complete the installation
  ```
  systemctl reboot
  ```

The `latest` tag will automatically point to the latest build. That build will still always use the Bazzite version specified in `recipe.yml`, so you won't get accidentally updated to the next major version.

## ISO

You can generate an offline ISO with the instructions available [here](https://blue-build.org/learn/universal-blue/#fresh-install-from-an-iso).

## Verification

These images are signed with [Sigstore](https://www.sigstore.dev/)'s [cosign](https://github.com/sigstore/cosign). You can verify the signature by downloading the `cosign.pub` file from this repo and running the following command:

```bash
cosign verify --key cosign.pub ghcr.io/vietsman/bc250-patched-kernel
```

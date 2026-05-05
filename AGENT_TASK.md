# AI Agent Task: Build Ubuntu 24.04 Root Filesystem

You are working inside GitHub Codespaces.

You need to build a master script `build-rootfs.sh` that takes:
- output root folder (default: ./rootfs)
- ubuntu-minimal-amd64-root.tar.xz (download from `https://cloud-images.ubuntu.com/minimal/releases/noble/release/ubuntu-24.04-minimal-cloudimg-amd64-root.tar.xz` if not downloaded)
- VNCviewer.deb (download from web if not provided)
- wallpaper.png (use OS installer default if not provided)
and produce an installed Ubuntu OS root directory. 

Your task is to create a reproducible build process that generates an Ubuntu 24.04 root filesystem under ./rootfs

The requirements for the Ubuntu 24.04 are in `REQUIREMENTS.md`.
Minimum disk space and GUI login speed are primary concerns.
Do not edit `REQUIREMENTS.md` unless explicitly instructed.

---

## Main goals

1. Read `REQUIREMENTS.md`.
2. Generate `build-rootfs.sh`.
3. Run `build-rootfs.sh`.
4. Inspect the generated filesystem under `./rootfs`.
5. Check whether every requirement in `REQUIREMENTS.md` is satisfied.
6. If a requirement is not satisfied, update `build-rootfs.sh`, rebuild, and inspect again.
7. Repeat until the result satisfies the requirements, or clearly document any requirement that cannot be satisfied.
8. Generate `verify-rootfs.sh`.
9. Generate `VERIFY_REPORT.md`.

---

## Expected output

After completion, the repository should contain:

```text
build-rootfs.sh
verify-rootfs.sh
VERIFY_REPORT.md
rootfs

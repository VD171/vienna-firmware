# vienna-firmware

🇬🇧 English · [🇧🇷 Português](README.pt-BR.md)

📒 **Every build and every hash: [CATALOG.md](CATALOG.md)**

Stock firmware for the **Motorola Edge 60 Neo** (`XT2509-1`, codename `vienna`, MT6878 / Dimensity 7400):
the **official fastboot package, minus `super`**. **One branch per build**, with the files at its root, each
exactly as Motorola shipped it, every file checked against the MD5 Motorola writes into its own `flashfile.xml`.

## Why without `super`

`super` holds `system`, `vendor`, `product` and friends. It is ~8 GB in 31 sparse chunks, far above what git on
GitHub can hold (100 MB per file), and it is the part you almost never need. Everything else is here, and
that is what you need to **recover the boot chain, unroot, or put back a single partition**: `boot`,
`init_boot`, `vendor_boot`, `vbmeta`, `dtbo`, `lk`, `logo`, the modem and the co-processor firmware.

If you do need a full ROM, get the complete package from Motorola's own tool (Rescue and Smart Assistant /
LMSA). The per chunk MD5s of `super` are in the published `flashfile.xml` of each build, so you can still
verify it against Motorola's manifest.

## Builds

| Build | Android | Branch |
|---|---|---|
| `W1UIS36H.39-17-8` | 16 | [`MMI-W1UIS36H.39-17-8`](https://github.com/VD171/vienna-firmware/tree/MMI-W1UIS36H.39-17-8) |

The images are **region agnostic**: this is the `regulatory-DEFAULT` (Global) package. Retail and regulatory
identity live on the device's own regulatory partition, not in the firmware, so the same images serve any
region on the same build. No device specific identity is contained in them.

## Layout

| Where | What |
|---|---|
| **`main`** (this branch) | the READMEs and [`CATALOG.md`](CATALOG.md): one table per build with file, partition, size, SHA-256, MD5, and whether the MD5 matches Motorola's |
| **one branch per build** (`MMI-<build>`, same naming as [vienna-kernel-source](https://github.com/VD171/vienna-kernel-source)) | every file of the package at the root, original names, plus `SHA256SUMS`, `MD5SUMS` and Motorola's `flashfile.xml` / `servicefile.xml` / `signing-info.txt` |

`modem.img` (112 MB) is above GitHub's 100 MB limit, so it is stored as `modem.img.part00` + `modem.img.part01`.
`cat` them back in order; the checksum lists cover the parts and the original file.

## Verify

```bash
git clone --depth 1 --single-branch -b MMI-W1UIS36H.39-17-8 https://github.com/VD171/vienna-firmware
cd vienna-firmware
cat modem.img.part00 modem.img.part01 > modem.img
sha256sum -c --ignore-missing SHA256SUMS
md5sum    -c --ignore-missing MD5SUMS
```

## Flashing

Bootloader unlocked, device in fastboot. Put back **one partition at a time**, on the active slot:

```bash
fastboot flash init_boot init_boot.img   # unroot: stock ramdisk back
fastboot flash boot boot.img             # stock kernel
fastboot flash vendor_boot vendor_boot.img
fastboot flash vbmeta vbmeta.img
```

> ⚠️ **Only flash images of the build that is installed on your device.** This device has **no BROM
> recovery** (MT6878, SLA/DAA protected): a wrong `preloader`, `lk`, `tee` or `efuse` is a brick with no way
> back, and `signing-info.txt` shows anti-rollback is enforced on the bootloader chain.
>
> ⚠️ **Do not run `flashfile.xml` blindly.** It erases `nvdata`, `userdata` and `metadata`, and it expects the
> `super` chunks that are not here. `servicefile.xml` is the same sequence without the `userdata` wipe.

## Related

| Link | What |
|---|---|
| 🛠 [VD171/vienna-kernel-build](https://github.com/VD171/vienna-kernel-build) | root: KernelSU-Next LKM patched into `init_boot`, one release per KSU-Next build |
| 📦 [VD171/vienna-kernel-source](https://github.com/VD171/vienna-kernel-source) | the kernel sources, extracted, one branch per tag |
| 🧵 [XDA thread](https://xdaforums.com/t/guide-rooting-how-to-root-motorola-60-edge-neo-5g-xt2509-1-vienna.4798267/) | `[GUIDE][ROOTING]` XT2509-1 (vienna) |

## Contact

| Channel | Address |
|---|---|
| Site | https://vd171.ru |
| Site | https://vd.priv8.ru |
| Telegram | [@VD_Priv8](https://t.me/VD_Priv8) |
| Discord | [@VD.Priv8](https://discord.com/users/1296831918989639721) |
| E-mail | vd.priv8@pm.me |
| XDA-Developers | [@VD171](https://xdaforums.com/m/vd171.4699873/) |
| GitHub | [@VD171](https://github.com/VD171) |

## License

The repo's own text (READMEs, catalog, checksum lists) is [MIT](LICENSE). **The firmware is property of
Motorola / Lenovo** and is redistributed here, unmodified, only to help recovery and unroot. It is not
relicensed.

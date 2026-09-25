# vienna-firmware · `W1UIS36H.39-17-8`

🇬🇧 English · [🇧🇷 Português](README.pt-BR.md) · [⬅ all builds (`main`)](https://github.com/VD171/vienna-firmware)

Stock firmware of the **Motorola Edge 60 Neo** (`XT2509-1`, `vienna`), build **`W1UIS36H.39-17-8`**
(Android 16): the official fastboot package, **minus `super`**, every file at the root of this branch.

| | |
|---|---|
| Fingerprint | `motorola/vienna_g_sys/vienna:16/W1UIS36H.39-17-8/d2b9a8-78a3a:user/release-keys` |
| Package | RETBR, `subsidy-DEFAULT`, `regulatory-DEFAULT` (Global, region agnostic), cid 50 |
| Integrity | the MD5 of every flashable file matches the one in Motorola's own [`flashfile.xml`](flashfile.xml) |
| Hash table | [CATALOG.md on `main`](https://github.com/VD171/vienna-firmware/blob/main/CATALOG.md) |

## Get it

```bash
git clone --depth 1 --single-branch -b MMI-W1UIS36H.39-17-8 https://github.com/VD171/vienna-firmware
cd vienna-firmware
cat modem.img.part00 modem.img.part01 > modem.img   # see below
sha256sum -c --ignore-missing SHA256SUMS
```

Single files: open the file on GitHub and use **Download raw file**.

## `modem.img` is split

GitHub refuses files above 100 MB in git, and `modem.img` is 112 MB. It is stored as `modem.img.part00` +
`modem.img.part01`; `cat` them back in order. `SHA256SUMS` / `MD5SUMS` list both the parts and the original
`modem.img`, so the rebuilt file is checked against Motorola's MD5.

## Not here

- `super.img` (31 sparse chunks, ~8 GB). Its per chunk MD5s are in [`flashfile.xml`](flashfile.xml), so a full
  package obtained elsewhere (Motorola's LMSA) can still be verified.
- `slcf_mediatek_default_v1.0.atc` and `regulatory_info_default.png` **are** here, as the zero byte placeholders
  they are in the official package.

> ⚠️ Only flash images of the build installed on your device: there is no BROM recovery on this device, and a
> wrong `preloader`, `lk`, `tee` or `efuse` is a brick. Do not run `flashfile.xml` blindly: it wipes
> `nvdata`/`userdata`/`metadata` and expects the `super` chunks. Details in the
> [main README](https://github.com/VD171/vienna-firmware#flashing).

Firmware is property of Motorola / Lenovo, redistributed unmodified only to help recovery and unroot.

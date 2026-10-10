# vienna-firmware catalog

| Channel | Address |
|---|---|
| Site | https://vd171.ru |
| Site | https://vd.priv8.ru |
| Source | https://github.com/VD171/vienna-firmware |
| GitHub | [@VD171](https://github.com/VD171) |
| XDA-Developers | [@VD171](https://xdaforums.com/m/vd171.4699873/) |
| Telegram | [@VD_Priv8](https://t.me/VD_Priv8) |
| Discord | [@VD.Priv8](https://discord.com/users/1296831918989639721) |
| E-mail | vd.priv8@pm.me |

Every published build, and a SHA-256 and MD5 for every file. The MD5 column is checked against the
MD5 that Motorola itself writes into `flashfile.xml`: ✅ means the file is byte for byte what
Motorola shipped. The same lists live as `SHA256SUMS` / `MD5SUMS` at the root of each build's branch, ready for
`sha256sum -c` / `md5sum -c`.

## Builds

| Build | Android | Fingerprint | Package | Files | Branch |
|---|---|---|---|---|---|
| `W1UI36H.39-25-11-4` | 16 | `motorola/vienna_g_sys/vienna:16/W1UI36H.39-25-11-4/2734cd-58da6:user/release-keys` | `subsidy-DEFAULT`, `regulatory-DEFAULT` (Global), cid 50 | 35 (no `super`) | [`MMI-W1UI36H.39-25-11-4`](https://github.com/VD171/vienna-firmware/tree/MMI-W1UI36H.39-25-11-4) |
| `W1UIS36H.39-17-8` | 16 | `motorola/vienna_g_sys/vienna:16/W1UIS36H.39-17-8/d2b9a8-78a3a:user/release-keys` | `subsidy-DEFAULT`, `regulatory-DEFAULT` (Global), cid 50 | 35 (no `super`) | [`MMI-W1UIS36H.39-17-8`](https://github.com/VD171/vienna-firmware/tree/MMI-W1UIS36H.39-17-8) |

## `W1UI36H.39-25-11-4`

| File | Partition | Size (bytes) | SHA-256 | MD5 | Motorola MD5 |
|---|---|---:|---|---|:-:|
| `apusys.img` | `apusys_a` | 1185936 | `43393f97b152394376b6262419399003f4459581db42a6841ca1a3e4f5336dbc` | `e83d5c10423c6d3fc9440680b5511c6d` | ✅ |
| `boot.img` | `boot_a` | 67108864 | `f8a5f539754947deeb54bf80a1927e93b5807c81f0fca7aab04cbc8ee25ac919` | `11c55a7ebd97642035ecbe92a10416fe` | ✅ |
| `ccu.img` | `ccu_a` | 103168 | `c4ed53063f41ee7803bc972315e15af2d456d3921ae7ff65c9c97070d1fdf277` | `690d251fe6b9b7561432477dc84791a6` | ✅ |
| `cid_template.dat` | `-` | 44 | `e0622885c2ee758d2e5db14a15113801672207142ac73a67fe53053d060b4898` | `fd086fc89b910d6b0dc51ff1925adb2c` | n/a |
| `connsys_bt.img` | `connsys_bt_a` | 1510688 | `c5a9df03871c23d29eb184834436f16f982a1ba326b53e047dbf7ad8c9e3208e` | `855271f9b539aa88f377a7e222623175` | ✅ |
| `connsys_gnss.img` | `connsys_gnss_a` | 527680 | `8187c0bdca335305b05b7c83ffe351a16e48ab3f07d9ecd1602e48322c17e300` | `0209cbef7dd62f5e7fbc4ee83a7463fd` | ✅ |
| `connsys_wifi.img` | `connsys_wifi_a` | 3163424 | `bfde5528c89f2c0a1e57028590e2875f0102e75caa1783d80f54673711573fe5` | `a2102874dcead9272bc00a8616a3c1e6` | ✅ |
| `dpm.img` | `dpm_a` | 905024 | `16aabb709694aac81a2bdde5018e66b6676bdd817740e99a3da52ae7ed82e0a3` | `cd714baa88789a0544a6c59227c2c8a1` | ✅ |
| `dtbo.img` | `dtbo_a` | 8388608 | `9a442cf2d48b02001c6a002ce03f29099edd1a41da1e5eb74492f91cf06feda6` | `16b107abf3acd403e8d33e27e6ba74b5` | ✅ |
| `efuse.img` | `efuseBackup` | 4816 | `ac6fbb176725065bef0b5ec3d7109139463e57914585be369f3c7cad12f2a457` | `ecda4a747907cd0e595c45e24fa95a4e` | ✅ |
| `flashfile.xml` | `-` | 8416 | `17c2fad9875e021e35fef00e3e9f0bdaf96ed29f4874a7884fef130ca4a9a5fd` | `613dff5c5ecef8d8c7bd74b790fe0138` | n/a |
| `gpueb.img` | `gpueb_a` | 529184 | `514df1261a6f27e732d3053482624acc3fe151a46bea21dd398bf471f27cd113` | `fd44ed089cc746ae93f2d5cb78663ce8` | ✅ |
| `gz.img` | `gz_a` | 3337200 | `1e8d3667425fa85221d9796ab79556811952cd9ccb16b58e427214a5b8aaefc6` | `7a0a9d003adc85d5b2e6b6be3efe8248` | ✅ |
| `init_boot.img` | `init_boot_a` | 8388608 | `59b64d0e216cc3aa08f125799b52d89cb2d60029a155a80b564ed32e1d297ba8` | `d860680d10dc704ff17c8341dbd22ca8` | ✅ |
| `lk.img` | `lk_a` | 4401136 | `ded99ed4ad86f5bebcdde8048bb730e69a9eea18716d8793c42bdd7911adc59d` | `8740758cceed17aecb7e2f513ba156d0` | ✅ |
| `logo.img` | `logo_a` | 20234528 | `c6641ed9398295d0790c5b7449a142041ad0b7d50c20cff5a4b85cdbb7ed6e74` | `873775402ef30e7d7bbcd8db4158b5a7` | ✅ |
| `mcf_ota.img` | `mcf_ota_a` | 29999104 | `ddb3ec18345918ff3c18175c247841cbcff4c26e703860a85daaf2c44f063c24` | `3f857df8cc44ee27a03283e41b2684fd` | ✅ |
| `mcupm.img` | `mcupm_a` | 713344 | `dc04ab339bc3f8e42fb16860ff21b2ae7ba61dfaa5a86cda16bdf29ca2ea79de` | `559fb073f18529a9bc60ee5fcb0cce62` | ✅ |
| `modem.img ¹` | `modem_a` | 112854800 | `feb97463c765edd334e798e1db0aed716f3e34ecabb92e765ea5deda2ece23df` | `19232404bf5e3a713506c464fb68a2b6` | ✅ |
| `PGPT` | `gpt` | 32768 | `eab74cfc6127c284cf40cb62d236595a225a99b364b8799c7d80645ae1fed84e` | `3bd225df7521cee9bd9f1bd08c598a2d` | ✅ |
| `pi_img.img` | `pi_img_a` | 63808 | `8f512f99f1317a1f693453f5c22b881e70c0cdd02693266387c95c81f128555b` | `b56971ccdb74a211c2bb3eeeaa13e275` | ✅ |
| `preloader.img` | `preloader` | 865316 | `44604e6aadc8f35916fcc1f0946c95f887e2fc4afe37f546d7b50b113a319f4f` | `b449a5c2a4838dc304d506a57caef751` | ✅ |
| `regulatory_info_default.png` | `-` | 0 | `e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855` | `d41d8cd98f00b204e9800998ecf8427e` | n/a |
| `scp.img` | `scp_a` | 10456224 | `1d6fda2b491a46648d5c5aa1770bfec265f43ddcd0ea839491d62c294e7f2166` | `6aa8208bed7592a93836201abe1c4fdc` | ✅ |
| `servicefile.xml` | `-` | 8188 | `ee5a9438fd833af944507ccff80dcca897e54e05b75bcdc45f818585a7a57697` | `aa4d4b68e5162235af8fb956f3a5471c` | n/a |
| `signing-info.txt` | `-` | 2244 | `30bc4f1987db26faa1ee9ad49d5ceb5ef35b31144c6d62a7d327c58bcdd031d2` | `18d7f1b8999d6488596e5cd8b5cbc936` | n/a |
| `slcf_mediatek_default_v1.0.atc` | `-` | 0 | `e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855` | `d41d8cd98f00b204e9800998ecf8427e` | n/a |
| `spmfw.img` | `spmfw_a` | 18000 | `61032778638a39f7e74fcd6802903775c3946904ddb237f5f6cea385fcee6c80` | `08c64ca62332b9eaf0c3e759b2b285b8` | ✅ |
| `sspm.img` | `sspm_a` | 887808 | `48af2bfe2cca9593ef0ef638cf8a8bfd3ed01eb516f2279994d2df9f485e79cd` | `053ba675941fad91bbb2081094309853` | ✅ |
| `tee.img` | `tee_a` | 1538304 | `4d3bd0dfdd03344962c43e7cb372cd49b4fdc347f4a8086e3e178f252c74fccf` | `bf5ba8f0cccc1f11f2386804f454d0f1` | ✅ |
| `vbmeta.img` | `vbmeta_a` | 8192 | `654e7f9fcf3c7f18a4f3c143cb68fa16ae383f09960547ccaf55b0ded10405e3` | `ba8bc7629d0ed924f574eda78437c423` | ✅ |
| `vbmeta_system.img` | `vbmeta_system_a` | 4096 | `1528d9c7b325c1c3ac41a94b87f418523fd4e871a56b01a5f51e9903012754b9` | `47c54ea3511ed1a93202ac90123f9fad` | ✅ |
| `vcp.img` | `vcp_a` | 1487552 | `b5ed688b2efffc143e4b7a6132a43f08062d303cf1ec738e54decc4286a599c7` | `4554747c0aed39e725e6a700876ddb35` | ✅ |
| `vendor_boot.img` | `vendor_boot_a` | 67108864 | `5a0c47aaf3f9852d758de53901ab23411de1afca4706083d0b2f1531774bfa49` | `8646132038a3c3313945f2724643e175` | ✅ |
| `VIENNA_G_SYS_W1UI36H.39-25-11-4_subsidy-DEFAULT_regulatory-DEFAULT_cid50_CFC.info.txt` | `-` | 553 | `787bfca6e7b21d8d65e848442965b258474df8eb6274d80884e3f4d38019e1c9` | `127ad0122afa81419a5d69815969f9ac` | n/a |

`n/a` = the file is not flashed, so `flashfile.xml` carries no MD5 for it (metadata, manifests, or the
two zero byte placeholders, which exist in the official package and are kept only for completeness).

¹ stored in the branch as `modem.img.part00` + `modem.img.part01` (GitHub's 100 MB limit); `cat` them back.
The parts are listed in the branch's `SHA256SUMS` / `MD5SUMS` too.

### `super` (not published here)

`super.img` is ~8 GB (31 sparse chunks) and is not redistributed. Its per chunk MD5s are in the
official [`flashfile.xml`](https://github.com/VD171/vienna-firmware/blob/MMI-W1UI36H.39-25-11-4/flashfile.xml), so a full package obtained elsewhere can still be
verified against Motorola's own manifest.

## `W1UIS36H.39-17-8`

| File | Partition | Size (bytes) | SHA-256 | MD5 | Motorola MD5 |
|---|---|---:|---|---|:-:|
| `apusys.img` | `apusys_a` | 1185936 | `a9b02cca8659dfb71e7fd4d4afa0c12edb333312fdf48775af33a7e89add9c7d` | `bc1b2c32ed3404ea819225b203ffb6fa` | ✅ |
| `boot.img` | `boot_a` | 67108864 | `f4b0014ccb246ff586f38eaf2c791293bb2a46d07bfe9ad13f1b2684838cf48a` | `3951fd069596cb49bb312dbe35c9107b` | ✅ |
| `ccu.img` | `ccu_a` | 103152 | `bea2e6f2389c9775a3408f7817eb131be9119ec861e60a75542d030fbfaad5c2` | `a98b2e6a5cabda120674a1a52053d680` | ✅ |
| `cid_template.dat` | - | 44 | `e0622885c2ee758d2e5db14a15113801672207142ac73a67fe53053d060b4898` | `fd086fc89b910d6b0dc51ff1925adb2c` | n/a |
| `connsys_bt.img` | `connsys_bt_a` | 1510688 | `5c9227b0a3b86eb91ea0db61942e27559ce171e0a2866d3e5e828cc747326edb` | `af66f805c873270d1fa81a2e632802ab` | ✅ |
| `connsys_gnss.img` | `connsys_gnss_a` | 527680 | `f154e1263e0447c08072e7f0f1c3cdddba3639fdf55528ce62e6eb21bfc574ba` | `2549163b3ac4bf44cc48509212a983ef` | ✅ |
| `connsys_wifi.img` | `connsys_wifi_a` | 3163424 | `9b4d98da5c6ec679000a1640ee385c87f607b2471e4679794cb13fa3cd7a8cf0` | `6909134c7027550d7c3339f4a06382f9` | ✅ |
| `dpm.img` | `dpm_a` | 905024 | `cda7a040e1daeb69c94692772d4ce644cbae3a91ba597cef902dda717aa2ad4c` | `60bd643a2be8aeb1fc7c1565ecbdc931` | ✅ |
| `dtbo.img` | `dtbo_a` | 8388608 | `33c1637f643465171bac91fc7b0327b74284f02c6bf6a9217123e0c895fb8358` | `4e84583b84d062395df305093b00f538` | ✅ |
| `efuse.img` | `efuseBackup` | 4816 | `5db0e3f9c6fb40419cd36c69dddebfac9ff134c670e99633219a77c95463f91b` | `9d2a47a176af8825fa58225b54984262` | ✅ |
| `flashfile.xml` | - | 8414 | `73b1ef10c11b0b0e495539aa5572781bf3f55c5e6ab091c5007e2f23ee6f82ce` | `9c4c1ea90022577e7e80c13937c0abe1` | n/a |
| `gpueb.img` | `gpueb_a` | 529184 | `03d4ac50d7e7532ae23b36dbeb1915db4dd7fb1e8794af9ebcff9a0e2dda2ad0` | `5b8cec982fef6cc8f566a3920d3b1e31` | ✅ |
| `gz.img` | `gz_a` | 3337200 | `915ca0e2f7cf7a993a5d1fb4ca9f6aa8df52c42f26b9fe9507827946535f4904` | `7977e94e0ae5e92c18cb03325f70e2f9` | ✅ |
| `init_boot.img` | `init_boot_a` | 8388608 | `c9e74cd5e90380ef6a173b85df1d33e08a78f11f77f0d0fb94a9f8bc410ab6dc` | `9591556c9fafdfc815b9afeacd9d7b54` | ✅ |
| `lk.img` | `lk_a` | 4392944 | `ef806a95bda720284c541176890407d0b842cfc76104e86c8a10f2ab1fd6f8fd` | `e0ba88077f7012cc777c91bd90604478` | ✅ |
| `logo.img` | `logo_a` | 20234528 | `0a260f627e80194e883959dbcc4ac2ecbc96bc8156f5ec3b7690beb3533f59f3` | `707fc34237c2a61225bfb9b28ad7e1ef` | ✅ |
| `mcf_ota.img` | `mcf_ota_a` | 29999104 | `bb39ca3a71d9424d2152611f18c15ee96ae5eb039908d4465dde568e01079133` | `dd7ee3a3696c228a89755a53da0a4130` | ✅ |
| `mcupm.img` | `mcupm_a` | 713344 | `c036c446d3e994267585bef5e206d0b5496a5baa23ee7172f7d90db07aad4210` | `d6dd49419607c28f28ec6742c8d23ac6` | ✅ |
| `modem.img` ¹ | `modem_a` | 112854800 | `62545d23aabcab9ab8aff31f15626182ebe383de005ce846df989b44dd236c31` | `e075c9d8a087947edab81cfddb49c4dc` | ✅ |
| `PGPT` | `gpt` | 32768 | `3e39839e38db871acba73b420ed0abbcb4f4f3835b91a574f30d61342fb56659` | `593bd037b8a107d33218872bb7ff0571` | ✅ |
| `pi_img.img` | `pi_img_a` | 63808 | `c15d3247bda63fcceac7d673723437b9969661e3b26c81c05e0b9a0849e9149c` | `7d65c11fe20824fe143f26d2cdf81aba` | ✅ |
| `preloader.img` | `preloader` | 865316 | `4332e3423d1ab50848f33df0f1350a9762842f659907b46c032095748ea9852c` | `4a428d69726f7db9b16508b5f96d5b7b` | ✅ |
| `regulatory_info_default.png` | - | 0 | `e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855` | `d41d8cd98f00b204e9800998ecf8427e` | n/a |
| `scp.img` | `scp_a` | 10456224 | `620583a7f75d500e57bc1cc9af186e123b3d03cdfc8f67a659f1eea78e0000cb` | `c6ae76ca0749a4059ec7276c3e7a1662` | ✅ |
| `servicefile.xml` | - | 8186 | `57067a24f8c755c1ad6a853a40b40caea273b8329c30ba42b1cef343db91df15` | `70baae85d1fea57e23b7577b29d92399` | n/a |
| `signing-info.txt` | - | 2244 | `270291224744b27325424e07532085fd2e10f425d269b2457044aa2da9865301` | `b35806b065632e8126b0f32e9688580a` | n/a |
| `slcf_mediatek_default_v1.0.atc` | - | 0 | `e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855` | `d41d8cd98f00b204e9800998ecf8427e` | n/a |
| `spmfw.img` | `spmfw_a` | 18000 | `aca321fc404b360c0ab3b12aba3520c946b8e127600f645697416e5bfa15c5c9` | `95b60732f35ea07b4a534099bae6fd3d` | ✅ |
| `sspm.img` | `sspm_a` | 887808 | `e38336c7f1104ad19fa101e2297a2a1279876d3530dda184b98dfbdcc0e7bcec` | `bcbe6562af809f1f6cea09bd433064f1` | ✅ |
| `tee.img` | `tee_a` | 1538304 | `e885f5c23215b3d0cc5de7fcfb01074eb740b2c45b48779a7dd3888d99d9410b` | `d3084f09c54f919c5450cbb3b292bbd3` | ✅ |
| `vbmeta.img` | `vbmeta_a` | 8192 | `46ef7e1807d99d0e6435806fb0e72a09725483dc5499d3f44d6714b14874f6ab` | `dd69c26da58e287e0f957589afc2189b` | ✅ |
| `vbmeta_system.img` | `vbmeta_system_a` | 4096 | `27ae75e7ac7fba6f33885926ddbc37c9219eaf4598ce65e473fe7aed7b14689b` | `396590c36a418f6a1e66ff61c9d7d7a6` | ✅ |
| `vcp.img` | `vcp_a` | 1487552 | `a8cf7cf67d148c2806b9f0bb2e515f29043cd0e58037d727508d72c8e17972f9` | `eacc991014a6e0f741ba5f58f634b49d` | ✅ |
| `vendor_boot.img` | `vendor_boot_a` | 67108864 | `c106d7bf760347e44b400d3543f8f77efd8c4bbfa2198b08f67b679ecf04f180` | `a5378febfac165ebcc9249d2e4dedca2` | ✅ |
| `VIENNA_G_SYS_W1UIS36H.39-17-8_subsidy-DEFAULT_regulatory-DEFAULT_cid50_CFC.info.txt` | - | 545 | `3f89ec05f96cb822b34a0c2cccfc2c5de9042b8922e2747f0ab5918294979907` | `bc6a4db9e277220d94c28b324e1320ac` | n/a |

`n/a` = the file is not flashed, so `flashfile.xml` carries no MD5 for it (metadata, manifests, or the
two zero byte placeholders, which exist in the official package and are kept only for completeness).

¹ stored in the branch as `modem.img.part00` + `modem.img.part01` (GitHub's 100 MB limit); `cat` them back.
The parts are listed in the branch's `SHA256SUMS` / `MD5SUMS` too.

### `super` (not published here)

`super.img` is ~8 GB (31 sparse chunks) and is not redistributed. Its per chunk MD5s are in the
official [`flashfile.xml`](https://github.com/VD171/vienna-firmware/blob/MMI-W1UIS36H.39-17-8/flashfile.xml), so a full package obtained elsewhere can still be
verified against Motorola's own manifest.

# vienna-firmware · `W1UI36H.39-25-11-4`

[🇬🇧 English](README.md) · 🇧🇷 Português · [⬅ todas as builds (`main`)](https://github.com/VD171/vienna-firmware/blob/main/README.pt-BR.md)

Firmware stock do **Motorola Edge 60 Neo** (`XT2509-1`, `vienna`), build **`W1UI36H.39-25-11-4`** (Android 16):
o pacote fastboot oficial, **sem o `super`**, com todos os arquivos na raiz desta branch.

| | |
|---|---|
| Fingerprint | `motorola/vienna_g_sys/vienna:16/W1UI36H.39-25-11-4/2734cd-58da6:user/release-keys` |
| Pacote | `subsidy-DEFAULT`, `regulatory-DEFAULT` (Global, não depende de região), cid 50 |
| Integridade | o MD5 de cada arquivo gravável bate com o do [`flashfile.xml`](flashfile.xml) da própria Motorola |
| Tabela de hashes | [CATALOG.md na `main`](https://github.com/VD171/vienna-firmware/blob/main/CATALOG.md) |

## Baixar

```bash
git clone --depth 1 --single-branch -b MMI-W1UI36H.39-25-11-4 https://github.com/VD171/vienna-firmware
cd vienna-firmware
cat modem.img.part00 modem.img.part01 > modem.img   # veja abaixo
sha256sum -c --ignore-missing SHA256SUMS
```

Arquivo solto: abra o arquivo no GitHub e use **Download raw file**.

## O `modem.img` está dividido

O GitHub recusa arquivos acima de 100 MB no git, e o `modem.img` tem 112 MB. Ele está guardado como
`modem.img.part00` + `modem.img.part01`; junte com `cat`, na ordem. O `SHA256SUMS` / `MD5SUMS` lista as partes e
também o `modem.img` original, então o arquivo remontado é conferido contra o MD5 da Motorola.

## O que não está aqui

- `super.img` (31 pedaços esparsos, ~8 GB). Os MD5 de cada pedaço estão no [`flashfile.xml`](flashfile.xml),
  então o pacote completo baixado em outro lugar (LMSA da Motorola) ainda pode ser conferido.
- `slcf_mediatek_default_v1.0.atc` e `regulatory_info_default.png` **estão** aqui, vazios como no pacote oficial.

> ⚠️ Só grave imagens da build instalada no seu aparelho: não há recuperação por BROM, e `preloader`, `lk`,
> `tee` ou `efuse` errado é brick. Não rode o `flashfile.xml` às cegas: ele apaga `nvdata`/`userdata`/`metadata`
> e espera os pedaços do `super`. Detalhes no [README da `main`](https://github.com/VD171/vienna-firmware/blob/main/README.pt-BR.md#gravar).

O firmware é propriedade da Motorola / Lenovo, redistribuído sem modificação só para ajudar em recuperação e
remoção de root.

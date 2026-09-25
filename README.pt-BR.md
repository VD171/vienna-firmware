# vienna-firmware

[🇬🇧 English](README.md) · 🇧🇷 Português

📒 **Todas as builds e todos os hashes: [CATALOG.md](CATALOG.md)**

Firmware stock do **Motorola Edge 60 Neo** (`XT2509-1`, codinome `vienna`, MT6878 / Dimensity 7400): o
**pacote fastboot oficial, sem o `super`**. Uma release por build, cada arquivo exatamente como a Motorola
distribuiu, todos conferidos com o MD5 que a própria Motorola grava no `flashfile.xml`.

## Por que sem o `super`

O `super` guarda `system`, `vendor`, `product` e companhia. São ~8 GB em 31 pedaços esparsos, muito acima do
que uma release comporta (2 GiB por arquivo), e é a parte que você quase nunca precisa. Todo o resto está
aqui, e é o que você precisa para **recuperar a cadeia de boot, tirar o root ou devolver uma partição**:
`boot`, `init_boot`, `vendor_boot`, `vbmeta`, `dtbo`, `lk`, `logo`, o modem e os firmwares dos coprocessadores.

Se precisar da ROM inteira, baixe o pacote completo pela ferramenta da própria Motorola (Rescue and Smart
Assistant / LMSA). Os MD5 de cada pedaço do `super` estão no [`flashfile.xml`](builds/) publicado, então dá
para conferir mesmo assim contra o manifesto da Motorola.

## Builds

| Build | Android | Release |
|---|---|---|
| `W1UIS36H.39-17-8` | 16 | [W1UIS36H.39-17-8](https://github.com/VD171/vienna-firmware/releases/tag/W1UIS36H.39-17-8) |

As imagens **não dependem de região**: este é o pacote `regulatory-DEFAULT` (Global). A identidade de varejo
e de regulamentação mora na partição regulatory do próprio aparelho, não no firmware, então as mesmas imagens
servem qualquer região na mesma build. Nenhuma identidade de aparelho está contida nelas.

## Organização

| Onde | O quê |
|---|---|
| **Assets da release** | as imagens, com os nomes originais, mais `SHA256SUMS` e `MD5SUMS` |
| [`builds/<build>/`](builds/) | os mesmos `SHA256SUMS` / `MD5SUMS`, o `flashfile.xml`, o `servicefile.xml` e o `signing-info.txt` da Motorola, as informações da build e os dois arquivos vazios do pacote |
| [`CATALOG.md`](CATALOG.md) | uma tabela por build: arquivo, partição, tamanho, SHA-256, MD5 e se o MD5 bate com o da Motorola |

## Conferir

```bash
# na pasta onde você baixou os arquivos
sha256sum -c --ignore-missing SHA256SUMS
md5sum    -c --ignore-missing MD5SUMS
```

## Gravar

Bootloader destravado, aparelho em fastboot. Devolva **uma partição por vez**, no slot ativo:

```bash
fastboot flash init_boot init_boot.img   # tirar o root: ramdisk stock de volta
fastboot flash boot boot.img             # kernel stock
fastboot flash vendor_boot vendor_boot.img
fastboot flash vbmeta vbmeta.img
```

> ⚠️ **Só grave imagens da build que está instalada no seu aparelho.** Este aparelho **não tem recuperação
> por BROM** (MT6878, protegido por SLA/DAA): `preloader`, `lk`, `tee` ou `efuse` errado é brick sem volta, e o
> `signing-info.txt` mostra que há anti-rollback na cadeia do bootloader.
>
> ⚠️ **Não rode o `flashfile.xml` às cegas.** Ele apaga `nvdata`, `userdata` e `metadata`, e espera os pedaços
> do `super` que não estão aqui. O `servicefile.xml` é a mesma sequência sem apagar o `userdata`.

## Relacionados

| Link | O quê |
|---|---|
| 🛠 [VD171/vienna-kernel-build](https://github.com/VD171/vienna-kernel-build) | root: KernelSU-Next LKM no `init_boot`, uma release por build do KSU-Next |
| 📦 [VD171/vienna-kernel-source](https://github.com/VD171/vienna-kernel-source) | as fontes do kernel, extraídas, um branch por tag |
| 🧵 [Tópico no XDA](https://xdaforums.com/t/guide-rooting-how-to-root-motorola-60-edge-neo-5g-xt2509-1-vienna.4798267/) | `[GUIDE][ROOTING]` XT2509-1 (vienna) |

## Contato

| Canal | Endereço |
|---|---|
| Site | https://vd171.ru |
| Site | https://vd.priv8.ru |
| Telegram | [@VD_Priv8](https://t.me/VD_Priv8) |
| Discord | [@VD.Priv8](https://discord.com/users/1296831918989639721) |
| E-mail | vd.priv8@pm.me |
| XDA-Developers | [@VD171](https://xdaforums.com/m/vd171.4699873/) |
| GitHub | [@VD171](https://github.com/VD171) |

## Licença

O texto próprio do repo (READMEs, catálogo, listas de hash) é [MIT](LICENSE). **O firmware é propriedade da
Motorola / Lenovo** e está redistribuído aqui, sem modificação, só para ajudar em recuperação e remoção de
root. Não é relicenciado.

# RickyOS Fonts

[RickyOS](https://github.com/chinoryunqin/RickyOS)（Read Pico 阅读器系统）“在线下载字体”使用的字体目录。

| 字体 | 来源 | 字号 |
| --- | --- | --- |
| RickySans | 思源黑体 Source Han Sans CN 2.005 | 12–32 |
| RickySerif | 思源宋体 Source Han Serif CN 2.003 | 12–32 |
| LXGWWenKai | 霞鹜文楷 LXGW WenKai v1.522 | 12–32 |
| RickyGrin | 得意黑 Smiley Sans v2.0.1（上游仅含简体） | 12–32 |
| RickyBookSong | 霞鹜新致宋 LXGW Neo ZhiSong v1.067 | 12–32 |
| ZhuqueFangsong | 朱雀仿宋 Zhuque Fangsong v0.212 | 12–32 |
| RickyRound | 思源柔黑 Resource Han Rounded | 12–32 |

字号为 12–32 之间的双数。v1.1.0 新增后三款字体和 24–32 号大字，原有 4 款 12–22 号的文件与 v1.0.2 逐字节相同。

## 为什么这样裁剪

每款字体只含常规体，字符集为 GB2312（全部 6763 字）、Big5 一级常用字、3500 常用字，以及拉丁字母、标点和常用符号，并补齐了相邻的少量字使区间数不超过 4000。这样每个 `.cpfont` 都不超过 6,549,504 字节，阅读器可以把它整份放进 Flash 加速缓存，翻页时不必再从 SD 卡逐字读取。

## 文件

- `fonts/*.cpfont`：cpfont v4 字体文件，文件名为 `<字体>_<字号>.cpfont`
- `fonts.json`：清单，下载地址指向本仓库同版本的 GitHub Release
- `mirror.json`：同一份清单，下载地址经 jsDelivr 镜像本仓库的 `fonts/`

两份清单的 `mirrors` 列出其他存放相同文件的地址，某个文件下载失败时阅读器会依次换用。
- `sources.json`：每款字体的原始文件、许可证地址及 SHA256
- `SHA256SUMS`：字体、许可证和清单文件的校验和

文件由 RickyOS 仓库的 `scripts/build_rickyos_font_catalog.py` 生成，源文件都按 URL 和 SHA256 锁定。

## 许可证

除 RickyBookSong 外，各字体均以 [SIL Open Font License 1.1](https://openfontlicense.org) 授权，许可证全文见 `fonts/<字体>-OFL.txt`。这些文件经过子集化和格式转换，属于 OFL 意义上的修改版本，因此不使用保留字体名：思源字体（保留名 “Source”）改称 RickySans / RickySerif，思源柔黑（含保留名 “Source” 的部分）改称 RickyRound，得意黑（保留名 “Smiley”“得意黑”）改称 RickyGrin。霞鹜文楷和朱雀仿宋没有保留字体名，沿用原名。

RickyBookSong 是霞鹜新致宋的衍生字体，按 IPA Font License 1.0 授权，许可证全文见 `fonts/RickyBookSong-IPA.txt`，衍生说明见 `fonts/RickyBookSong-NOTICE.txt`。

- 思源黑体、思源宋体 © Adobe
- 霞鹜文楷 © LXGW；© The Klee Project Authors
- 霞鹜新致宋 © LXGW；IPA
- 朱雀仿宋 © Zhejiang JadeFoci Technology
- 思源柔黑 © Cyano Hao；部分 © Adobe
- 得意黑 © atelierAnchor

---

Font catalog for RickyOS's online font download. Regular-only cpfont v4 subsets of Source Han Sans/Serif CN, LXGW WenKai, Smiley Sans, LXGW Neo ZhiSong, Zhuque Fangsong and Resource Han Rounded, in sizes 12–32, covering common Simplified and Traditional Chinese, each file sized to fit the reader's flash cache. All are under the SIL OFL 1.1 except RickyBookSong (IPA Font License 1.0); renamed builds avoid the Reserved Font Names.

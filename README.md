# RickyOS Fonts

[RickyOS](https://github.com/chinoryunqin/RickyOS)（Read Pico 阅读器系统）“在线下载字体”使用的字体目录。

| 字体 | 来源 | 汉字 | 字号 |
| --- | --- | --- | --- |
| RickySans | 思源黑体 Source Han Sans CN 2.005 | 9726 | 12–22 |
| RickySerif | 思源宋体 Source Han Serif CN 2.003 | 9726 | 12–22 |
| LXGWWenKai | 霞鹜文楷 LXGW WenKai v1.522 | 9726 | 12–22 |
| RickyGrin | 得意黑 Smiley Sans v2.0.1（上游仅含简体） | 6840 | 12–22 |

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

所有字体均以 [SIL Open Font License 1.1](https://openfontlicense.org) 授权，各自的许可证全文见 `fonts/<字体>-OFL.txt`。这些文件经过子集化和格式转换，属于 OFL 意义上的修改版本，因此不使用保留字体名：思源字体（保留名 “Source”）改称 RickySans / RickySerif，得意黑（保留名 “Smiley”“得意黑”）改称 RickyGrin。霞鹜文楷没有保留字体名，沿用原名。

- 思源黑体、思源宋体 © Adobe
- 霞鹜文楷 © LXGW；© The Klee Project Authors
- 得意黑 © atelierAnchor

---

Font catalog for RickyOS's online font download. Regular-only cpfont v4 subsets of Source Han Sans/Serif CN, LXGW WenKai and Smiley Sans, covering common Simplified and Traditional Chinese, each file sized to fit the reader's flash cache. All fonts are under the SIL OFL 1.1; renamed builds avoid the Reserved Font Names.

# Manual in Chinese for `PGF/TikZ`

`PGF/TikZ` 宏包使用手册中文译版

![CI](https://github.com/rnicrosoft-studio/pgf-tikz-manual-chinese/workflows/CI/badge.svg)

This repository is forked from the official repository and uses the same `Github Action` workflow as the official does as CI tool,
so that the latest release version can be obtained directly without compilation by yourself.
And it will be more convenient for pull request (welcomed!) review.

Only `luatex` and `xelatex` engines are considered in manual compilation.
`luatex` is suggested by the original manual and will have a higher priority.
Actually, the original source skipped some chapters in other engine's versions.

* Original source: https://github.com/pgf-tikz/pgf/tree/master/doc/generic/pgf
* Original manual: https://github.com/pgf-tikz/pgf/releases
* Translation source: https://github.com/rnicrosoft-studio/pgf-tikz-manual-chinese/tree/master/doc/generic/pgf
* Translation release: https://github.com/rnicrosoft-studio/pgf-tikz-manual-chinese/releases

## Translation progress
* [x] 封面
* [ ] (working) 版权
* [ ] (working) 目录
* [ ] (working) 引言 Introduction
* [ ] Part I - 教程和指南 Tutorials and Guidelines
* [ ] Part II - 安装和配置 Installation and Configuration
* [ ] Part III - TikZ 不是绘图程序 TikZ ist kein Zeichenprogramm
* [ ] Part IV - 图形绘制 Graph Drawing
* [ ] Part V - 库 Libraries
* [ ] Part VI - 数据可视化 Data Visualization
* [ ] Part VII - 工具 Utilities
* [ ] Part VIII - 数学和面向对象引擎 Mathematical and Object-Oriented Engines
* [ ] Part IX - 基础层 The Basic Layer
* [ ] Part X - 系统层 The System Layer
* [ ] Part XI - 引用和索引 References and Index

## Reference
* https://github.com/Hansimov/pgfmanual-zh Someone seems that have abandon the translation work

---

## `README.md` in the original repository

# pgf – A Portable Graphic Format for TeX

![CI](https://github.com/pgf-tikz/pgf/workflows/CI/badge.svg)

PGF is a TeX macro package for generating graphics. It is platform-
and format-independent and works together with the most important TeX
backend drivers, including `pdftex` and `dvips`. It comes with a
user-friendly syntax layer called Ti*k*Z.

See the directory `doc/generic/pgf` for more information. See the file
`doc/generic/pgf/pgfmanual.pdf` (also available from 
https://pgf-tikz.github.io/pgf/pgfmanual.pdf) for a manual. This
documentation also explains the installation.  See the file
`doc/generic/pgf/license/LICENSE` for license details.

Please go to the official repository at https://github.com/pgf-tikz/pgf or the
official mailing list at https://tug.org/mailman/listinfo/pgf-tikz to submit
bug reports, request new features, etc.

We also have a chat on the Matrix network at
[#pgf-tikz:matrix.org](https://matrix.to/#/#pgf-tikz:matrix.org).

## Installation

In general you should just use the version of PGF that is shipped by
your TeX distribution.  See their documentation on how to install
packages.

If you are feeling adventurous you can install the latest development
version in TeX Live from our tlcontrib repository.
```console
$ tlmgr repository add http://pgf-tikz.github.io/pgf/tlnet pgf-development
$ tlmgr pinning add pgf-development "*"
$ tlmgr update --self --all
$ tlmgr install pgf --reinstall
```

## Development

Currently PGF does not have a comprehensive test suite to check for
regressions, so for now we check for bugs by building the manual for
each commit.  To build the manual locally you can either copy the PGF
repository into your texmf tree (not recommended) or use the usertree
option of TeX Live.  For the usertree option on GNU/Linux, follow
these steps:
```console
$ git clone https://github.com/pgf-tikz/pgf
$ tlmgr init-usertree --usertree pgf
$ export TEXMFHOME=$(readlink -f pgf)
$ cd pgf
$ texlua build.lua manual luatex
```
We recommend building at least the version for LuaTeX, as shown in the
example above because this has the broadest coverage of PGF features.
To test the animations feature you have to build the version for
dvisvgm.

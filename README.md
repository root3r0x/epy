# `$ epy`

![screenshot](https://raw.githubusercontent.com/wustho/epy/master/screenshot.png)

CLI Ebook Reader.

This is just a fork of my own [epr](https://github.com/wustho/epr) with these extra features:

- Supported formats:
  - Epub (.epub, .epub3)
  - FictionBook (.fb2)
  - Mobi (.mobi)
  - AZW3 (.azw3), some but not all (see [KindleUnpack](https://github.com/kevinhendricks/KindleUnpack))
- Reading progress percentage
- Bookmarks
- External dictionary integration (`sdcv` or `dict`)
- Inline formats: **bold** and _italic_ (depend on terminal and font capability. Italic only supported in python>=3.7)
- Text-to-Speech (with additional setup, read [below](#text-to-speech))
- [Double Spread](#double-spread)

# Installation

## Via PyPI

```shell
$ pip3 install epy-reader
```

## Via Pip+Git

```shell
$ pip3 install git+https://github.com/wustho/epy
```

# Reading Tips Using Epy

When reading using `epy` you might occasionally find triple asteriks `***`.
That means you reach the end of some section in your ebook and the next line (right after those three asteriks, which is in new section) will start at the top of the page.
This might be disorienting, so the best way to get seamless reading experience is by using next-page control (`space`, `l` or `Right`) instead of next-line control (`j` or `Down`).

# Configuration File

Config file is available in json format which is located at:

- Linux: `~/.config/epy/config.json` or `~/.epy/config.json`
- Windows: `%USERPROFILE%\.epy\config.json`

Although, there are not many stuffs to configure.

# Using Mouse

Pretty useful when running `epy` on Termux Android.

| Key | Action |
| --- | --- |
| `Left Click` (right side of screen) | next page |
| `Left Click` (left side of screen) | prev page |
| `Right Click` | ToC |
| `Scroll Up` | scroll up |
| `Scroll Down` | scroll down |
| `Ctrl` + `Scroll Up` | increase text width |
| `Ctrl` + `Scroll Down` | decrease text width |

# Text-to-Speech

To get Text-to-Speech (TTS) support, you need to install these external dependencies:

- `pico2wave` (from `libttspico-utils` package (Ubuntu) or `svox-pico-bin` package (AUR))
- `play` (from `sox` package)

eg.

```shell
$ # Ubuntu
$ apt install libttspico-utils sox

$ # Arch
$ yay -S svox-pico-bin
$ pacman -S sox
```

And then make sure `pico2wave` and `play` is in `$PATH`.

# Double Spread

Double spread is intended to mimic the behaviour of real book, so line scrolling navigation will act as scrolling page and textwidth is not adjustable.

# Tip Jar

[PayPal](https://paypal.me/wustho)

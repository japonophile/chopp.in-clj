---
layout: post
title: "Release Notes"
date: "2007-02-11"
---

**1.13** (April 16, 2008)

- Fix broken "Send to Editor" button in WP 2.3.x
- Fix compatibility problem with some plugins (e.g. qtranslate...) implicitly relying on jQuery
- Unescape special characters in caption

**1.12** (April 13, 2008)

- Fix bug in option page (WP<2.5)
- Support watermark in thumbnails and alpha blending PNG-24 watermarks (thanks to [Michael Yates](http://www.dayates.com.au/) for his contribution!)
- Make alt tag configurable
- Update translations

**1.11** (April 12, 2008)

Fix title bug (thanks to KV for reporting it), enhance caption handling.

**1.10** (April 11, 2008)

Major update:

- Support WP2.5!
- Fix several bugs (a.o. problem with multiple upload)
- Support German and Danish (thanks to Raphael Hofer and Georg S. Adamsen for their contribution!)
- Support "Insert into Excerpt"
- Use WP standard CSS for alignment
- Allow caption even with rich text editor
- ... and more!

**1.9** (October 15, 2007)

Fix for invisible upload options with IE.

**1.8** (October 14, 2007)

- Fix unclosed img tag when suppressing title (thanks to Clark for reporting the problem!)
- Fix problem with deleting attachments (thanks to Jimmy for reporting the problem!)

**1.7** (October 6, 2007)

Fix multi-language to use plugin domain (thanks to Pim for mentioning this!)

**1.6** (October 5, 2007)

New features!

- Multi-language support: I started with my favorites, French and Japanese. Contributions for other languages are welcome: please send me your .po files.
- Integration of [multifile upload](http://wordpress.ex-libris.jp "Multifile Upload plugin") plugin functionality
- Support for HighslideJS and LightWindow
- Allow specifying watermark option per post
- Default resizing reference side separate for thumbnail and resize
- Specify content of image title
- Memory and system limits checking
- Tested on WP2.3

**1.5** (April 16, 2007)

- Do not enlarge pictures (thanks to [Jaap](http://www.beulbek.nl/) for reporting it)
- Do not insert Lightbox (etc.) "rel" tag for non-image attachments (WP2.1.x) (thanks to Nick D for reporting it)

**1.4**

- Fix a bug in caption for WP2.1.x (thanks to miuprint for reporting the problem)
- Allow to put watermark signature in the top-right corner, and rotate it (thanks to [Cheezburger](http://www.icanhascheezburger.com) for his contribution)

**1.3**

- Show image resizing and thumbnail options only when selecting an image attachment
- Support other plugins than Lightbox (e.g. Greybox, Thickbox) and open image in another window
- Allow specifying max height or max width, instead of max largest side, and support cropping (thanks to [Christer Olsson](http://www.ljusaideer.se) for his contribution to this feature)
- Basic option page to configure the above settings, and help page
- An attempt to solve the invisible "Upload"/"Send to Editor" button.
- Support WP ME (sorry, not for WP mu yet)

**1.2**

This release targets WP 2.0.x (nothing new for WP 2.1):

- Support WP versions older than 2.0.4
- Fix invisible "Upload" button (by increasing iframe size, currently only works for 2.0.x)

**1.1**

Made left/right/center alignment optional

**1.0**

Initial release


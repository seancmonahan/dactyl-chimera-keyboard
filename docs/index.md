## Dactyl Chimera build guide

This build guide is a work in progress. It is written for the Dactyl Chimera EX branch. It does not apply to any existing release.

### Is Dactyl Chimera right for me?

Dactyl Chimera (DC) is a 5 row, 6 column keyboard on each half. You can add an extra inner column if you want to, but you'll need to find a new place for the microcontroller.

Building DC requires access to a 3d printer, soldering equipment, and a Windows, Mac, or Linux computer. If you don't own a 3D printer, check your local public library, makerspace, or college.

You won't need to know how to write programs or open the command line to enjoy the Dactyl Chimera . However, you will not have OLED displays, per-key RGB backlight, or thumbstick support without modifying some C files and working in the Linux command line.

Dactyl Chimera is designed for MX-style switches. As of 2021-10-17 there is no Choc switch support.

### Designing your keyboard layout

Start thinking about your layout now! You'll want your software to be ready when the keyboard is done printing.

#### Understanding the basic theories of keyboard layout design:

For beginners, I'd recommend reading at least one of the following:

- Thomas Baart's Guide to working with a small keyboard. https://blog.splitkb.com/how-to-work-with-small-keyboards
- Currently there is only one link in this list...

Once you're beyond the basics, you might want to check out:

- DreymaR's explanation of "[Extend](https://dreymar.colemak.org/layers-extend.html)", for where to put your arrow keys.
- [Precondition's Guide to Home Row Mods](https://precondition.github.io/home-row-mods) **VS** [why you shuold BAN Key Chords](http://xahlee.info/kbd/banish_key_chords.html) for where to put shift, ctrl, and more.
- I use Colemak mod-DH and highly recommend it. It helps my fingers rest on the keyboard instead of hovering above it. It's easy to learn using the [Tarmak](https://dreymar.colemak.org/tarmak.html) system!
- Finally, I challenge someone to combine [Asetniop](http://asetniop.com/) with 50 macro keys. There is no reward.

#### But what do I do with all these keys?

I get it: having anything bigger than a 40% may be intimidating to some of you... but you don't actually need to USE all the keys on this keyboard. You don't even need to put switches into all the holes. Dactyl Chimera needs to be massive so that it can accommodate all types of layouts, big and small. That said, even if you stick with a smaller layout, you may want to fill the top and bottom rows with macros. These "extra keys" can be used to quickly accommodate a strange keyboard shortcut, (for example, "why does Microsoft Excel force me to use F2 as the Edit Cell shortcut?"), to temporarily patch a deficit in your layout, ("I didn't realize I needed an Enter key on my left hand!"), or for actions you often take when your hands aren't settled into a typing rhythm. (my top picks include "Leave Zoom Meeting" and "mute computer".)

#### But I use a full size keyboard! Where are my arrow keys and function row?

Dactyl Chimera has almost as many keys as a 60% keyboard, depending on your thumb cluster choice. Included with each release is a spreadsheet showcasing the best layouts available. The Traditional-ish layout should appease fans of bigger keyboards.

### Buying components



### Hand sizing chart, and using 3D modeling software



### how to 3d print the pieces

Print the racks first, then the columns from innermost to outermost, and finally the thumb cluster.

#### The Racks:

RackA and RackB are your keyboard's bottom plate. If you're completely new to 3D printing, it should be as simple as drag-and-dropping the file into the printer's slicer and hitting "Go". RackA and RackB can also be laser-cut or CNC milled out of a variety of materials; .dwg and .svg are provided for your convenience.

RackC, also known as RackStagger, is also very simple, however, it may be your first introduction to support material, but your 3D printing software might decide it's not necessary. You should print this part upright, just like it is in the .stl file. Your print may have issues sticking to the print bed. A heated bed, a "brim" (enabled in the 3d printing software) or a layer of glue from a water-soluble glue stick should help. If you still encounter issues, the excellent community over at https://www.reddit.com/r/FixMyPrint/

RackD is a large piece, but it shouldn't be too much of a challenge. All you really need to do is make sure support material is turned on. If you are printing at a public printer, insist that the gap between the support material is not increased from its default setting in the slicing software. The curve's overhang is quite steep and it'll need close support to look good. If you're using PrusaSlicer, I recommend using the [variable layer height](https://help.prusa3d.com/en/article/variable-layer-height-function_1750) feature. For removing support material, the tools to use are a pair of flush cuters and a pair of needle nose pliers. Do not use knives or chisels to remove the support material. You will cut into the print, or worse, cut yourself. You will also wear safety glasses to protect your eyes from tiny bits of flying plastic.

#### The Arches:

Pring the inner most arch, the one with 4 switch holes, first. Do this because when something inevitably goes wrong, you'll have wasted less plastic. Lay the part flat on its side, with the "legs" that support the arch flat against the printer's build plate. If you are using PrusaSlicer, set the seam position to the under the arch between each socket, and restrict support material from being generated near the clip overhangs of the sockets. Once you get the hang of things you can print multiple arches at once. Remember, you have a total of 10 arches to print; 5 for each side.

After printing each arch, check to make sure the switches and screws fit.

Finally, print the microcontroller holder, tenting foot, thumb cluster, and any other accessories you desire. There are various choices for each available, and none should be particularly difficult to make.

### soldering and wiring

The wiring matrix for Dactyl Chimera looks like this:

Dactyl Chimera is designed for hotswap sockets. Solder togetner a mesh/web of sockets together, making sure to leave generous amounts of wiring for the changes between column height. Arch 2, aka the ring finger, needs to be "woven" into the mesh becuase it has no gaps on the underside.

If you choose to wire by hand anyway, refer to [the QMK hand-wiring guide](https://docs.qmk.fm/#/hand_wire). You might also find it useful to extend the length of the switch pins, as explained in [the Squeezebox blog](https://peterlyons.com/problog/2021/04/squeezebox-keyboard/)

If you desire RGB, check out Wolf Icefang's S-S-S-S-P-C-B (super simple single switch printed circuit board) which can hold SK68 mini-e RGB LEDs in place without changing anything else about the wiring process! It's coming soon!

Make sure to socket your microcontroller. This is not "optional" like in some keyboards; it is necessary to take advantage of the swappable thumb cluster feature. **Links explaining socketing due to show up soon.**

Unlike some low-profile keyboards, Dactyl Chimera is usb port-side up. To be more accurate, the VCC pin is in the upper right corner.

This keyboard uses RJ-9 jacks to eliminate the issues of shorting over a TRRS cable. Here are close-up photos of how that is wired.

### Software and firmware



You can use the [editor on GitHub](https://github.com/WolfIcefang/dactyl-chimera-keyboard/edit/build-guide/docs/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/WolfIcefang/dactyl-chimera-keyboard/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

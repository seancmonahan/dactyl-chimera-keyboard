## Dactyl Chimera build guide

This build guide is a work in progress. It is written for the Dactyl Chimera EX branch. It does not apply to any existing release.

### Is Dactyl Chimera right for me?

Dactyl Chimera (DC) is a 5 row, 6 column keyboard on each half. You can add an extra inner column if you want to, but you'll need to find a new place for the microcontroller.

Building DC requires access to a 3d printer and soldering equipment. You'll also need access to your own personal Windows, Mac, or Linux computer.

You don't "need" to write code or open the command line to set up or use Dactyl Chimera. However, you cannot have OLED displays, per-key RGB backlight, or thumbstick support without modifying some C files and working in the Linux command line.

Dactyl Chimera is designed for MX-style switches. It is not compatible with ALPs, Choc, Topre, or any brand of optical keyswitch.

### Designing your keyboard layout

Start thinking about your layout now! You'll want your software to be ready when the keyboard is done printing.

#### Understanding the basic theories of keyboard layout design:

For beginners, I'd recommend reading at least one of the following:

- Thomas Baart's Guide to working with a small keyboard. https://blog.splitkb.com/how-to-work-with-small-keyboards
- Currently there is only one item in this list...

The features your keyboard has will be limited (or expanded) depending on the firmware you choose. The following are "officially supported" (which really just means I'll provide some files to help make the setup a bit easier.)
- The easiest user experience is provided by Vial. You can update your keyboard's layout instantly by dragging and dropping keycap-shaped tiles onto your keyboard layout. Learn about Vial here: https://get.vial.today/
- If you seek nigh-unlimited customization at the minor cost of a more complex layout updating method, QMK is the firmware for you. https://docs.qmk.fm/
- The one feature lacking in QMK is bluetooth support. That's where ZMK steps in. https://zmk.dev/ Please remember that Dactyl Chimera has no battery compartment and is NOT A PORTABLE KEYBOARD, so the need for wireless is extremely limited.
- There is plenty of other firmware out there, but you'll have to do the setup work yourself. The unabridged list can be found here: https://www.reddit.com/r/MechanicalKeyboards/wiki/firmware/

Once you know what your keyboard CAN do, it's time to figure out what you WANT it to do:

- DreymaR's explanation of "[Extend](https://dreymar.colemak.org/layers-extend.html)", for where to put your arrow keys.
- [Precondition's Guide to Home Row Mods](https://precondition.github.io/home-row-mods) **VS** [why you shuold BAN Key Chords](http://xahlee.info/kbd/banish_key_chords.html) for where to put shift, ctrl, and more.
- I use Colemak mod-DH and highly recommend it. It helps my fingers rest on the keyboard instead of hovering above it. It's easy to learn using the [Tarmak](https://dreymar.colemak.org/tarmak.html) system!
- Finally, I challenge someone to combine [Asetniop](http://asetniop.com/) with 50 macro keys. There is no reward.

You can join the https://www.reddit.com/r/KeyboardLayouts/ subreddit if you find you really love messing with layouts.

#### But what do I do with all these keys?

I get it: having anything bigger than a 40% may be intimidating to some of you... but you don't actually need to USE all the keys on this keyboard. You don't even need to put switches into all the holes. Dactyl Chimera needs to be massive so that it can accommodate all types of layouts, big and small. That said, even if you stick with a smaller layout, you may want to fill the top and bottom rows with macros. These "extra keys" can be used to quickly accommodate a strange keyboard shortcut, (for example, "why does Microsoft Excel force me to use F2 as the Edit Cell shortcut?"), to temporarily patch a deficit in your layout, ("I didn't realize I needed an Enter key on my left hand!"), or for actions you often take when your hands aren't settled into a typing rhythm. (my top picks include "Leave Zoom Meeting" and "mute computer".)

#### But I use a full size keyboard! Where are my arrow keys and function row?

Dactyl Chimera has almost as many keys as a 60% keyboard, depending on your thumb cluster choice. The thumb cluster should make layer access marginally more convenient, but that isn't good enough for everyone. Currently, the only keyboards I know of with an F-row and arrow keys are the keyboards that inspired the original Dactyl: the [Maltron](https://www.maltron.com/store/c34/Dual_hand_keyboards.html) and the [Kinesis Advantage 2](https://kinesis-ergo.com/shop/advantage2-refurbished/) Many projects are in the works, check them out if this build guide hasn't been updated in a while:
- Reddit User [RMTZ](https://www.reddit.com/user/rmTizi/)'s keyboard is still in development.
- MoErgo's [Glove80](https://geekhack.org/index.php?topic=114881.msg3086876) has not gone into production yet.
- ScarletSwordfish's beautiful(?) [AEK II Split](https://geekhack.org/index.php?topic=103804) requires parts from an old Apple keyboard and might end up being a personal project.

### Buying components

We'll need some tools (3d printer, soldering iron, etc.), some normal keyboard parts (switches, keycaps), and some special parts (screws, 3d printer filament.)

#### Let's start with tools.

Personally, I think it's a good idea to use publically available tools so that you can invest more money in the actual components of your keyboard. Check your local makerspace, public library, or college to see what they have on hand. Who knows, it might even be fancier than what you could afford on your own. If you do insist on owning your own tools, these lists should help you. Make sure to read the full build guide to understand how you'll actually USE these tools.

 - Keebio maintains a great list of soldering equipment. https://docs.keeb.io/soldering-tools#tip-cleanertinner
 - I'm not sure about 3d printer shopping guides; your suggestions would be helpful here.
 - If you need safety glasses, I recommend the Uvex Sperian, Uvex Protégé, and Pyramex Ztek. The clear lens variants are great for working indoors while still providing UV protection outdoors.

### Hand sizing chart and using FreeCAD



### how to 3d print the pieces

Print the racks first, then the columns from innermost to outermost, and finally the thumb cluster.

#### The Racks:

RackA and RackB are your keyboard's bottom plate. If you're completely new to 3D printing, it should be as simple as drag-and-dropping the file into the printer's slicer and hitting "Go". RackA and RackB can also be laser-cut or CNC milled out of a variety of materials; .dwg and .svg are provided for your convenience.

RackC, also known as RackStagger, is also very simple, however, it may be your first introduction to support material, but your 3D printing software might decide it's not necessary. You should print this part upright, just like it is in the .stl file. Your print may have issues sticking to the print bed. A heated bed, a "brim" (enabled in the 3d printing software) or a layer of glue from a water-soluble glue stick should help. If you still encounter issues, the excellent community over at https://www.reddit.com/r/FixMyPrint/

RackD is a large piece, but it shouldn't be too much of a challenge. All you really need to do is make sure support material is turned on. If you are printing at a public printer, insist that the gap between the support material is not increased from its default setting in the slicing software. The curve's overhang is quite steep and it'll need close support to look good. If you're using PrusaSlicer, I recommend using the [variable layer height](https://help.prusa3d.com/en/article/variable-layer-height-function_1750) feature. For removing support material, the tools to use are a pair of flush cuters and a pair of needle nose pliers. Do not use knives or chisels to remove the support material. You will cut into the print, or worse, cut yourself. You will also wear safety glasses to protect your eyes from tiny bits of flying plastic.

#### The Arches:

Pring the inner most arch, the one with 4 switch holes, first. Do this because when something inevitably goes wrong, you'll have wasted less plastic. Lay the part flat on its side, with the "legs" that support the arch flat against the printer's build plate. If you are using PrusaSlicer, set the seam position to the under the arch between each socket, and restrict support material from being generated near the clip overhangs of the sockets. Once you get the hang of things you can print multiple arches at once. Remember, you have a total of 10 arches to print; 5 for each side.

After printing each arch, check to make sure the switches and screws fit.

#### Everything else:

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

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

For beginners, I'd read one of the following getting started guides:

- Thomas Baart's Guide to working with a small keyboard. https://blog.splitkb.com/how-to-work-with-small-keyboards
- Currently there is only one item in this list...

The features your keyboard has will be limited (or expanded) by the firmware you choose. The following are "officially supported" (which really just means I'll provide some files to help make the setup a bit easier.)
- The easiest user experience is provided by Vial. You can update your keyboard's layout instantly by dragging and dropping keycap-shaped tiles onto a picture of your keyboard. Learn about Vial here: https://get.vial.today/
- If you seek nigh-unlimited customization at the cost of a more complex setup, QMK is the firmware for you. https://docs.qmk.fm/
- The one feature lacking in QMK is bluetooth support. That's where ZMK steps in. https://zmk.dev/ Please remember that Dactyl Chimera has no battery compartment and is NOT A PORTABLE KEYBOARD, so the need for wireless is extremely limited.
- There is plenty of other firmware out there, but you'll have to do the setup work yourself. The unabridged list can be found here: https://www.reddit.com/r/MechanicalKeyboards/wiki/firmware/

Once you know what your keyboard CAN do, it's time to figure out what you WANT it to do:

- DreymaR's explanation of "[Extend](https://dreymar.colemak.org/layers-extend.html)", for where to put your arrow keys.
- [Precondition's Guide to Home Row Mods](https://precondition.github.io/home-row-mods) **VS** [why you shuold BAN Key Chords](http://xahlee.info/kbd/banish_key_chords.html) for where to put shift, ctrl, and more.
- I use Colemak mod-DH and highly recommend it. It helps my fingers rest on the keyboard instead of hovering above it. It's easy to learn using the [Tarmak](https://dreymar.colemak.org/tarmak.html) system!
- You can join the https://www.reddit.com/r/KeyboardLayouts/ subreddit for some really mind-bending ideas.
- Finally, I challenge someone to combine [Asetniop](http://asetniop.com/) with 50 macro keys. There is no reward.

#### But what do I do with all these keys?

I get it: having anything bigger than a 40% may be intimidating to some of you... but you don't actually need to USE all the keys on this keyboard. You don't even need to put switches into all the holes. Dactyl Chimera needs to be massive so that it can accommodate all types of layouts, big and small. That said, even if you stick with a smaller layout, you may want to fill the top and bottom rows with macros. These "extra keys" can be used to quickly accommodate a strange keyboard shortcut, (for example, "why does Microsoft Excel force me to use F2 as the Edit Cell shortcut?"), to temporarily patch a deficit in your layout, ("I didn't realize I needed an Enter key on my left hand!"), or for actions you often take when your hands aren't settled into a typing rhythm. (my top picks include "Leave Zoom Meeting" and "mute computer".)

#### But I use a full size keyboard! Where are my arrow keys and function row?

Dactyl Chimera has almost as many keys as a 60% keyboard, depending on your thumb cluster choice. The thumb cluster should make layer access marginally more convenient, but I know that won't be good enough for everyone. Currently, the only keyboards I know of with an F-row and arrow keys are the keyboards that inspired the original Dactyl: the [Maltron](https://www.maltron.com/store/c34/Dual_hand_keyboards.html) and the [Kinesis Advantage 2](https://kinesis-ergo.com/shop/advantage2-refurbished/) Many projects are in the works, though; check these links out:
- Reddit User [RMTZ](https://www.reddit.com/user/rmTizi/)'s Naïve keyboard is in development.
- MoErgo's [Glove80](https://geekhack.org/index.php?topic=114881.msg3086876) has a finalized design but has not gone into production yet.
- ScarletSwordfish's beautiful(?) [AEK II Split](https://geekhack.org/index.php?topic=103804) requires parts from an old Apple keyboard and might end up being a personal project.

### Buying components

We'll need some tools (3d printer, soldering iron, etc.), some normal keyboard parts (switches, keycaps), and some special parts (screws, 3d printer filament.)

#### Let's start with tools.

Personally, I think it's a good idea to use publically available tools so that you can invest more money in the actual components of your keyboard. Check your local makerspace, public library, or college to see what they have on hand. Who knows, it might even be fancier than what you could afford on your own. If you do insist on owning your own tools, these lists should help you. Make sure to read the full build guide to understand how you'll actually USE these tools.

 - Keebio maintains a great list of soldering equipment. https://docs.keeb.io/soldering-tools#tip-cleanertinner
 - I'm not sure about 3d printer shopping guides; your suggestions would be helpful here.
 - If you need safety glasses, I recommend the Uvex Sperian, Uvex Protégé, and Pyramex Ztek. The clear lens variants are great for working indoors while still providing UV protection outdoors.

#### Normal keyboard parts (the keys).

First, the keyswitches. There are nigh-unlimited options here, look no further than [ThereminGoat's](https://www.theremingoat.com/) blog of 1,000 switches. There are plenty of arguments both ways on switch ergonomics. Lighter switch springs are easier to press, but heavy springs protect you from the sharp impact of bottoming out. Lighter switches are great for multi-key combos, and heavy switches might help out pressing one key at a time.

Personally, I recommend silent switches on the Dactyl Chimera. Without walls or gaskets, it can be difficult to reduce unwanted sounds. Silent switches have tiny rubber bumpers inside the switch itself! Many popular switches have a silent variant.

Stores that sell switches at a reasonable price include:
 - NovelKeys https://novelkeys.com/collections/switches
 - KBDFans https://kbdfans.com/collections/switches
 - The r/mechanicalkeyboards wiki has an extensive list https://www.reddit.com/r/MechanicalKeyboards/wiki/switch_suppliers but is probably in need of some upkeep.

Keycaps are also very important. They play a key role in your keyboard's look and feel.
 - Use the MechanicalKeyboards [Keycap Guides](https://www.reddit.com/r/MechanicalKeyboards/wiki/keycap_guides) to learn all about keycap shapes and materials
 - Then head over to [KeyCapSellers](https://www.reddit.com/r/MechanicalKeyboards/wiki/keycapsellers) for pricing tiers and to find your favorite vendor.

The keycaps featured on my Dactyl Chimera are Razer's PBT Upgrade Set and MaxKeyboard's south-facing RGB set.

### Hand sizing chart and using FreeCAD

*Dactyl Chimera's .stl files have similar spacing to a regular Dactyl / Dactyl Manuform. If you like the default Dactyl shape but need DC's shorter print times, you can skip this secion.*

In order to use FreeCAD, you need to download it. Do so here: https://www.freecadweb.org/ The bottom of this page also lists the various helpful communities for when something goes wrong.

For people who know what this means: Dactyl Chimera is currently **not compatible** with the [LinkStage3 branch.](https://www.freecadweb.org/), a.k.a. ThunderCAD. Some sketches automatically delete all of their constraints when opened.

FreeCAD has an [official manual](https://wiki.freecadweb.org/Manual) but FreeCAD can do a ton of stuff from Raytracing to architecture, and the manual is still a work in progress. I'll give you the basics here.

When you first open Dactyl Chimera in FreeCAD, you should see something like this.

Like a lot of software, the trickiest step is figuring out which button is the most important. In FreeCAD, that's the "Workbench" dropdown list: (it might be in a different location and a different color for you)

![image](https://user-images.githubusercontent.com/38160450/138741323-3e677a1e-5984-4150-b918-8e67fb78d1a6.png)

If you don't have a workbench dropdown list, use the View dropdown in the menu bar:

![image](https://user-images.githubusercontent.com/38160450/138741609-7195e519-66bd-4e6f-86e3-57d5c432d033.png)

FreeCAD is highly customizable; for new users that means it's easy to accidentally hide or rearrange very important buttons. If you get stuck at any point, don't hesitate to ask for help.

Each workbench provides a unique set of tools for doing different type of work. For example, the "Part" workbench is like an advanced version of Tinkercad, and the TechDraw workbench is for drawing in 2d without any effect on 3d, like in AutoCAD or Adobe Illustrator. For Dactyl Chimera, the most important workbenches are the "Part Design", "Sketcher", and "Spreadsheet" workbenches.

But wait! Before we get started, make sure to choose your favorite Mouse Navigation mode, as explained here: https://wiki.freecadweb.org/Mouse_navigation Not doing this is like playing Super Metroid with the default control scheme.

#### Part Design

The Part Design workbench is for navigating 3d space and extruding your 2d sketches. Once again, there are a few "very importanat" buttons hidden among a bunch of other buttons that have very specific use cases. You need to find the Create Body, Create Sketch, and Create Datum Plane buttons, as well as "Pad selected sketch" and Pocket selected sketch" buttons. They look like this:

![image](https://user-images.githubusercontent.com/38160450/138745612-2e0ba2d3-b624-4f3a-b0f5-871e31b9e9cd.png)

You will also need to locate your [Tree View](https://wiki.freecadweb.org/Tree_view), which lists all the different parts in your file. It looks like this:

![image](https://user-images.githubusercontent.com/38160450/138747077-9d407efe-86a0-4679-b6d8-50faf0b111a4.png)

If you cannot find it, you might be in the "Tasks" tab isntead of of the "Model" tab.

Double clicking on something in the Tree View will let you edit that thing, whatever it is. (You can usually press the Escape key to stop editing.) Clicking on an object once in tree view then pressing the spacebar will toggle its visibility. Hovering your mouse over an item Tree View will make its 3d Model "Glow", which helps you see the internals of an object like the Tenting Screw or to help you identify an unnamed item. The item has to be visible for the hover glow trick to work.

If you want to create a new component for your keyboard, like a rotary encoder add-on or a different type of thumb cluster, click the "Create a new Body" button. In FreeCAD, each [Body](https://wiki.freecadweb.org/PartDesign_Body) is a different solid part. When you export the model, each body will become a separate .stl file.

The Body's origin might be invisible, so find it in Tree View and toggle its visibility on.

Now that you can see your Origin, you might want to place down some Datum Planes. Datum Planes *can* help you do things align screw holes and provide the bounding edges for where your part begins and ends, but they are optional. Read more about Datum Planes here: https://wiki.freecadweb.org/PartDesign_Plane/en



### how to 3d print the pieces

Print the racks first, then the columns from outermost to innermost, and finally the thumb cluster.

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

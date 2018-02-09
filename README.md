# Programmer-Layout
Let's designing a keyboard layout for "Touch Typing" Code!

## Why?
To keep focus and stay in the flow while coding it will be nice if we could write code in a touch typing way.

And not having to look at each symbol key will typing (unless doing many typos!).

For the classic programming characters like: `( [ { * / | & + -`

As well, for the funny symbol functions e.g. :`->` `=>` `++=` `::` `/:` `===` `:>`
  
## How?
If you are reading this, there is a big chance you have already some muscle memory for typing
at least on a specific layout depending your language, country, computer keyboard, job ...

And most of the special characters and punctuation we need for writing code are
not placed in a way to be used without looking at the keyboard (in most of the layout)
(We can argue that maybe the classics staggered keyboard was never
intend to be used in a touch typing way! ;) ,
but I reassure you I created this layout to be used with a common keyboard).


So I propose you first of all to stay with the layout you already know, mainly for the alphabetic characters,
and mapping all the "special characters" to another "level" accessed easily with the Space-Bar as modifier.

And organize the mapping so as the characters the most use are easily accessible and grouped in a logical manner
to be easily memorized (first in the head, then in the muscles!)

And to map all the number digits yet to another level (accessible with `Space + Shift`), I propose on the top and the middle rows
of the right hand so the left hand can press `Space + Shift_L`.


For those who use language specific characters like Accented or Latin Script e.g.:`é à ç ß ì õ ü ¿`
we have now space on the "number row" for placing them all in direct access.

Once used with the programming part of the layout it gives you the possibility to maybe adopt an ergonomics ASCII
layout like [Colemak](https://colemak.com/), [Norman](https://normanlayout.info/compare.html) (mainly for the alphabetic characters)
adapted for writing code (usually you write in English) but still be able to write in your native language
in quasi touch typing manner (depending of your keyboard and key position).

(Of course it's not adapted to write a novel, but for programming)


For still having access to the space character we must use a tool to generate the space character
on release of the key (Space-Bar) when not used as a modifier.

For Linux on of this tool:
* [Xcape](https://github.com/alols/xcape)
* [At Home Modifier](https://github.com/lambdaloop/at-home-modifier-evdev)
* [Space2Ctrl](https://github.com/r0adrunner/Space2Ctrl)


## How To Do?
For now, I have just an XKB symbols config file `ttpl` with the "Programming Layout" mapping and minimal variant of QUERTY or AZERTY for the alphabetical mapping.

And a tiny script `progLayout` for launching setxkbmap and xcape at Xorg start (in xinit or with "startup applications" *(Gnome GUI)*)

I've try to integrate it in the Gnome Keymap Config but it's tedious,
and the config can change slightly from Desktop Environment will still based on Gnome!

Put the file [src/ttpl](https://github.com/JonasSprenger/Programmer-Layout/blob/master/src/ttpl) in `/usr/share/X11/xkb/symbols/`

Put the file [src/progLayout](https://github.com/JonasSprenger/Programmer-Layout/blob/60dc87910db668bf49224b98303b34c221ce76e6/src/progLayout) in your path like `/usr/local/bin/`

Configure it according to your needs, some examples:

	> // standard English (US) with the programming layout
	> setxkbmap us+ttpl

	> // Dvorak with the programming layout
	> setxkbmap 'us(dvorak)+ttpl'

	> // Azerty (FR) with option nodeadkeys and the programming layout
	> setxkbmap 'fr(nodeadkeys)+ttpl'

	> // A minimal version of Aserty (just the alpha chars) and custom number row and programming layout
	> setxkbmap 'ttpl+ttpl(azerty)+ttpl(nbr_row_custom)'

## TODO:
- [ ] An image of the layout on a staggered and an orthogonal keyboard, in EN and FR
- [ ] Some gif will typing different programming language
- [ ] Add Contrib and Request section.

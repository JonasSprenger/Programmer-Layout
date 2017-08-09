## Some notes and links on XKB

### Man/Gides:
https://www.charvolant.org/doug/xkb/html/xkb.html

### Blog:
https://medium.com/@damko/a-simple-humble-but-comprehensive-guide-to-xkb-for-linux-6f1ad5e13450
http://hack.org/mc/writings/xkb.html
http://artisan.karma-lab.net/redefinition-dun-clavier

### Q & A:
https://stackoverflow.com/questions/45021978/create-a-custom-setxkbmap-option
https://unix.stackexchange.com/questions/197452/how-does-one-use-the-setxkbmap-geometry-option

### Repo:
https://github.com/andrewgdotcom/keyboardio-xkb


### Useful commands

* Print the configuration assembled by setxkbmap:

`setxkbmap -print -verbose 10`

* For showing the true current config loaded in the current display:

`xkbcomp :0 -a -`

`xkbcomp :0 -a out.xkb         #To get the output in a file out.xkb`

* For printing a layout to .pdf:

`setxkbmap pr iconofr -print | xkbcomp - - | xkbprint -ll 2 -label name - - | ps2pdf - > pr.pdf & xreader pr.pdf`

`setxkbmap pr iconofr -print | xkbcomp - - | xkbprint -lg 2 - - | ps2pdf - > pr.pdf & xreader pr.pdf`

`setxkbmap pr iconofr -geometry 'typematrix(tm2030USB-102)' -print | xkbcomp - - | xkbprint -ll 2 -level1 -diffs - - | ps2pdf - > pr.pdf & xreader pr.pdf`

* This program reports changes in the fundamental components of the XKB keyboard state plus the
effective compatibility state.

`xkbwatch`




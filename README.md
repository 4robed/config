# Setup translate

## 1. Install dependencies 
* Intall xclip
> sudo apt-get install xclip
* Install urxvt
> sudo apt-get install rxvt-unicode
* Install JetbrainsMono font
> https://www.jetbrains.com/lp/mono/

## 2. Config urxvt and setup trans.sh
### Config urxvt
```
vim ~/.Xresources

#copy-and-paste-below-config
```

```
!! Colorscheme

! special
*.foreground: #93a1a1
*.background: #141c21
*.cursorColor: #afbfbf

! black
*.color0: #263640
*.color8: #4a697d

! red
*.color1: #d12f2c
*.color9: #fa3935

! green
*.color2: #819400
*.color10: #a4bd00

! yellow
*.color3: #b08500
*.color11: #d9a400

! blue
*.color4: #2587cc
*.color12: #2ca2f5

! magenta
*.color5: #696ebf
*.color13: #8086e8

! cyan
*.color6: #289c93
*.color14: #33c5ba

! white
*.color7: #bfbaac
*.color15: #fdf6e3

!! URxvt Appearance
URxvt.font: xft:JetBrainsMono:style=Regular:size=11
URxvt.boldFont: xft:JetBrainsMono-Bold:style=Bold:size=11
URxvt.italicFont: xft:JetBrainsMono-Italic:style=Italic:size=11
URxvt.boldItalicfont: xft:JetBrainsMono-BoldItalic:style=BoldItalic:size=11
URxvt.letterSpace: -1
URxvt.lineSpace: -1
URxvt.geometry: 92x24
URxvt.internalBorder: 24
URxvt.cursorBlink: true
URxvt.cursorUnderline: false
URxvt.saveline: 2048
URxvt.scrollBar: false
URxvt.scrollBar_right: false
URxvt.urgentOnBell: true
URxvt.depth: 24
URxvt.iso14755: false

!! Common Keybinds for Navigations
URxvt.keysym.Shift-Up: command:\033]720;1\007
URxvt.keysym.Shift-Down: command:\033]721;1\007
URxvt.keysym.Control-Up: \033[1;5A
URxvt.keysym.Control-Down: \033[1;5B
URxvt.keysym.Control-Right: \033[1;5C
URxvt.keysym.Control-Left: \033[1;5D

!! Copy Paste & Other Extensions
URxvt.perl-ext-common: default,clipboard,url-select,keyboard-select
URxvt.copyCommand: xclip -i -selection clipboard
URxvt.pasteCommand: xclip -o -selection clipboard
URxvt.keysym.M-c: perl:clipboard:copy
URxvt.keysym.M-v: perl:clipboard:paste
URxvt.keysym.M-C-v: perl:clipboard:paste_escaped
URxvt.keysym.M-Escape: perl:keyboard-select:activate
URxvt.keysym.M-s: perl:keyboard-select:search
URxvt.keysym.M-u: perl:url-select:select_next
URxvt.urlLauncher: firefox
URxvt.underlineURLs: true
URxvt.urlButton: 1
```
### Reload urxvt config
>  xrdb ~/.Xresources  

### setup trans.sh
```
vim /usr/local/bin/trans.sh

#copy-and-paste-below-code-to-trans.sh

rxvt -hold  -geometry 70x30+0+590 -e trans :vi  "`xclip -o`"
```
### set custom shortcut for trans.sh
![image](https://github.com/4robed/config/assets/54355222/688a1c37-568a-4b19-8dc6-31310645b9ba)

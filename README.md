# puush4linux

puush4linux is a Linux client for the popular screenshot host [puush](http://puush.me). puush4linux aims to reach feature parity with the official Windows puush client. It currently supports authentication, taking screenshots and file uploading.

## Installation

**Arch Linux** users may install the [puush4linux package](https://aur.archlinux.org/packages/puush4linux/) from the AUR, packaged by [/u/some_random_guy_5345](https://www.reddit.com/user/some_random_guy_5345).

1. Install dependencies: `bash`, `scrot`, `curl`, `xclip` and (optionally) `libnotify`. You can additionally use [maim](https://github.com/naelstrof/maim) and [slop](https://github.com/naelstrof/slop) instead of scrot; they're automatically detected and preferred over scrot (caveat: `-w` requires `xdotool` when using maim + slop, but slop's window selection tool makes up for it).
2. Download the puush file and copy it to `/usr/bin`.
3. Run `puush -l` in your terminal and enter your user name and password to log in.
4. Set up shortcuts in your window manager/desktop environment to your liking.
 Example (XFCE):
 ![xfce4 shortcut example](http://puu.sh/ktPr6/4ab02a679a.png)

## Usage

`puush <options> <filename>`

You do not need to specify the file name if you are going to use the script to take a screenshot.

### Options

`-q` - Don't show any notifications on the desktop. (Automatically turned on if libnotify isn't found on the system.)

`-c` - Copy the URL of the uploaded file to X clipboard. If this is not specified, the URL will be sent to stdout.

`-h` - Display help.

`-a` - Take a screenshot of an area and then upload it.

`-f` - Take a screenshot of the entire screen and upload it.

`-w` - Take a screenshot of the active window and upload it.

`-l` - (Re-)log in to puush with your username and password.

### Optional environment variables

`PUUSH_SCREENSHOT_DIR` - Directory in which to save screenshots. If defined, screenshots are not deleted after uploading. If not defined, "/tmp" is used.

`PUUSH_DATE_FORMAT` - Date format for file name. See `man date` for information. Default is "%d-%m-%Y-%H%M%S".

### Examples

`puush -c -a` - Take a screenshot of an area, upload it and put the link into the clipboard. (Equivalent to Ctrl+Shift+4 on Windows systems.)

`puush -q myfile.png` - Upload an image and print the uploaded file URL to stdout without displaying desktop notifications.

`env PUUSH_SCREENSHOT_DIR="$HOME/Pictures" PUUSH_DATE_FORMAT="%y-%m-%d_%H:%M" puush -f` - Take a screenshot of the entire screen, store it in the Pictures folder in the home directory and use date format YY-MM-DD_HH_MM for the filename.

## Author & License

Created by [Darwin](http://hpup.co) with ♥.

```
DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
            Version 2, December 2004

Copyright (C) 2004 Sam Hocevar <sam@hocevar.net>

Everyone is permitted to copy and distribute verbatim or modified
copies of this license document, and changing it is allowed as long
as the name is changed.

    DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

0. You just DO WHAT THE FUCK YOU WANT TO.
```

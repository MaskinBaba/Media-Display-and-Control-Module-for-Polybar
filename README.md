## Media Display and Control Module for Polybar

This module won't be always functioning correctly because of limitations of playerctl and integeration between linux and players.

![Screenshot](Screenshot.png)

<ins>Dependencies</ins>

* playerctl
* [Font Awesome 5](https://fontawesome.com/download) for symbol of media controls
<br />

## Configuring modules with polybar

Paste the module below in config file of Polybar:
```sh
[module/playing]
type = custom/script
tail = true
exec = ${Location_of_playing}
format-background = #0d1a28
interval = 3

[module/previous]
type = custom/text
content = "  "
content-background = #0d1a28
click-left = playerctl previous

[module/pause-pause]
type = custom/script
tail = true
exec = ${Location_of_play_button}
format-background = #0d1a28
click-left = playerctl play-pause
interval = 2

[module/forward]
type = custom/text
content = "  "
content-background = #0d1a28
click-left = playerctl next
```

Replace the value of `exec` with the location of the [Playing.sh](playing.sh) script and [play_button.sh](play_button.sh) and if wanted change the value of `interval` to the desired value(Recommended to use 2-3 because of its System Usage)
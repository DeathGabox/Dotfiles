[Qtile](http://www.qtile.org/)

[Guia](https://github.com/qtile/qtile/wiki/wallpapers)

---

Mi configuracion
Usar nitrogen
- Instalar
```
pacman -S nitrogen
```
[Autostart](https://github.com/DeathGabox/Dotfiles/blob/main/Config/Qtile/autostart.sh)
```
micro ~/.config/qtile/autostart.sh

---

#!/usr/bin/env bash
nitrogen --restore

---

chmod +x ~/.config/qtile/autostart.sh
```
- Hacer que el archivo de autoarranque lo ejecute qtile
Modifica ```~/.config/qtile/config.py```
Y escribe
```
import os
import subprocess
from libqtile import hook

@hook.subscribe.startup_once
def autostart():
    home = os.path.expanduser('~/.config/qtile/autostart.sh')
    subprocess.Popen([home])
```

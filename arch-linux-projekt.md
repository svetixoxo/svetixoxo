# arch-linux-projekt

## Einkaufsliste
- Raspberry Pi 5, 8 GB: RPI5-8GB
- Raspberry Pi SSD Kit, 256GB: RPI-SSDK-256
- Raspberry Pi Active Cooler: RPI5-ACOOL
- Raspberry Pi 27W USB-C Power Supply: RPI5NT5AB
- Micro HDMI Kabel, schwarz, 1,0m: RPI4-HDMI4
- KKSB Gehäuse für Raspberry Pi 5, GPIO Zugang: 7350001161648 (passt das mit SSD-HAT?)

## Installieren und Einrichten
### Arch Linux installieren
1. Merlin nochmal nach den ersten Schritten fragen (Vorkonfiguration)
2. `GRUB/UEFI` statt `EFI`
3. `SYSTEMD` auswählen
4. `VIM` als Editor

### WLAN-Treiber
- notwendige Pakete: `broadcom-wl`, `linux-headers`, `linux-firmware`, `pahole`, `grub`
- `lsblk` zeigt Laufwerke an
- USB-Stick mounten mit `mount /dev/sd… /mnt`
- alle Dateien installieren: `cd /mnt` und dann `pacman -U *.pkg.tar.zst`

#### WLAN verbinden
- `nmcli device wifi list`
- `nmcli device wifi connect "SSID" --ask` bzw. `nmcli device wifi connect "SSID" bssid B:S:S:I:D --ask`

### Hyprland konfigurieren
- `vim .config/hypr/hyprland.conf`
- `kb_layout = de`
- `$mainMod = SUPER` ändern zu `ALT`
- bei `exec-once` nur `waybar`

## Nützliches
### VIM
- mit `/` und `N` kann man bei `VIM` suchen
- `i` für Insert-Modus (schreiben)
- Schließen und Speichern mit `:wq` (write, quit)

### Sonstiges
- beim `root` deutsches Tastaturlayout: `loadkeys de-latin1` (`-` ist auf `ß`)
- Pakete installieren mit `sudo pacman -S`
- mehrere Pakete lassen sich bspw. so auf einmal installieren: `sudo pacman -S kitty asciiquarium sl wofi waybar nwg-displays`
- Benutzer in `wheels`-Gruppe, testen mit `groups` (`root` mit `su` aufrufen)
- Progamme automatisch im Hintergrund starten, bspw.: `kitty &`
- mit `OPT 1`, `OPT 2` usw. kann man zwischen verschiedenen Workspaces wechseln
- beim Installieren etc. muss nicht `J/n` getippt werden, sondern mit `Enter` wird großgeschriebene Option automatisch ausgewählt
- mit `TAB` kann man Befehle, Pfade usw. vervollständigen
- mit `sudo !!` kann man den vorigen Befehl als `sudo` ausführen, ohne den Befehl nochmal neu zu tippen

### Links
- weitere Kurzbefehle: https://readline.kablamo.org/emacs.html
- Unix-Beispiele: https://schmutzit.sievers.dev/r/unixporn
- Hyprland-Wiki: https://wiki.hyprland.org/Useful-Utilities/
- Packages: https://archlinux.org/packages/?sort=&q=&maintainer=&flagged=

## Offene Punkte
- Kompatibilität Raspberry-SSD und Arch Linux
- Kompatibilität Raspberry-Erweiterungen und Arch Linux
- wie Audio auf Raspberry Pi – Rooting (I/O) über Interface möglich?
- gleiche Tastatur und Maus auf Mac und Raspi nutzbar?

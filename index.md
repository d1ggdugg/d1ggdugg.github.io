### .m4v-Dateien in .mp4-Dateien konvertieren
Alle .m4v-Dateien als .mp4-Datei mit gleichem Namen speichern im aktuellen Ordner per Terminal unter MacOS mittels ffmpeg: <br>
```for i in *.m4v; do ffmpeg -i "$i" -c copy „${i%.*}.mp4"; done```<br>

### Video-Dateien komprimieren mit ffmpeg
```ffmpeg -i eingabe.mp4 -vcodec libx264 -crf 20 ausgbae.mp4```<br>

### Spotify Songs downloaden
[ritiek/spotify-downloader](https://github.com/ritiek/spotify-downloader)<br>
Fehler vermeiden: ```pip3 uninstall spotdl```<br>
```spotdl -s```(Song einfügen per Drag&Drop)<br>

```spotdl --playlist``` (Playlist einfügen per Drag&Drop)<br>
```spotdl --list NAME_DER_PLAYLIST.txt```<br>

### Videos/Filme konvertieren
[handbrake](https://handbrake.fr)<br>
[ffmpeg](https://ffmpeg.org)<br>

### Ausschnitte aus Final Cut Pro X exportieren
Anfang des Videos mit ```i``` und Ende mit ```o``` markieren und ```Video bereitstellen```<br>

### Einblendungen animieren mit Keyframe
Einblendung einer Bauchbinde mit einem Titel und nacheinanderfolgenden zwei Untertiteln. Gesamtspielzeit: 10 Sekunden.<br>

Aufbau: ```Überblenden und Bewegen```<br>
Aktion: ```Bewegen (Beschleunigung: ohne)```<br>
Abbau: ```Überblenden und Bewegen```<br>

| Animation | Titel         | Untertitel 1     | Untertitel 2     |
| --------- | ------------- | ---------------- | ---------------- |
| Aufbau    | 1 Sek.        | 1 Sek.           | 1 Sek.           |
| Aktion    | 8 Sek. (20px) | 3,5 Sek. (-20px) | 3,5 Sek. (-20px) |
| Abbau     | 1 Sek.        | 1 Sek.           | 1 Sek.           |

### Untertitel 1080p
Schriftart: Roboto<br>
Höhe: 925 von Unterkante<br>
Schriftfarbe: weiß<br>
Schatten: Weichzeichen: 5, Distanz: 4 Deckkraft: 70%<br>

### CPU-/GPU-Temperatur auslesen unter MacOS
[fanny](https://github.com/DanielStormApps/Fanny)<br>

### Erstellungsdatum von Dateien ändern unter MacOS per Terminal
```touch -mt YYYYDDHHMM ```<br>

### USB-Festplatte einbinden
[Link](https://jankarres.de/2013/01/raspberry-pi-usb-stick-und-usb-festplatte-einbinden/)<br>

### OCR scannen aus Dokumenten (auch Screenshots, pdf, etc.)
[OwlOCR](https://owlocr.com)<br>

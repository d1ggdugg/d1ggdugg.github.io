### .m4v-Dateien in .mp4-Dateien konvertieren
Alle .m4v-Dateien als .mp4-Datei mit gleichem Namen speichern im aktuellen Ordner per Terminal unter MacOS mittels ffmpeg: <br>
```for i in *.m4v; do ffmpeg -i "$i" -c copy „${i%.*}.mp4"; done```<br>

### Video-Dateien komprimieren mit ffmpeg
Video um die Hälfte reduzieren und komprimieren (357MB zu 7,8MB)<br>
```ffmpeg -i input.mp4 -vcodec h264 -acodec aac -crf 30 -vf "scale=iw/2:ih/2" output.mp4```<br>
Verkleinern und Tonspur entfernen<br>
```ffmpeg -i input.mp4 -an -vcodec h264 -crf 30 -vf "scale=iw/2:ih/2" output.mp4```<br>
-an = Tonspur entfernen, muss auf den input erfolgen<br>

### Spotify Songs downloaden
[ritiek/spotify-downloader](https://github.com/ritiek/spotify-downloader)<br>
Fehler vermeiden: ```pip3 uninstall spotdl```<br>
```spotdl url```(Song einfügen per Drag&Drop)<br>

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

### EXIF Meta-Daten auslesen, schreiben, ändern
[ExifTool](https://exiftool.org)
terminal: exiftool (Bild einfügen per Drag&drop)<br>

### Mehrere Dateien umbenennen / Formate ändern (jpeg --> jpg)
[How to rename multiple files at once on Mac](https://www.imore.com/how-rename-multiple-files-once-mac)<br>

### .mp3-Player für android
[Musicolet Musikplayer](https://play.google.com/store/apps/details?id=in.krosbits.musicolet&hl=de&gl=US)
Ganz einfacher Musik-Player ohne Werbung und nur für den Offline-Einsatz<br>

### Luminar 4 Ordner für Ersetzung Himmeln (SkyReplacement) unter MacOS
[Anleitung](https://www.dpreview.com/forums/thread/4444084)<br>

### Bilder umbenennen anhand der Exif-Daten unter MacOs
[ExifRenamer](https://www.qdev.de/?location=mac/exifrenamer)<br>

### WLAN Stärke alle 0,5 Sekunden per Terminal konrollieren unter MacOS
```while x=1; do /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport -I | grep CtlRSSI; sleep 0.5; done ```<br>

### USB-Stick im exfat-Format unter Linux (raspberrypi) einbinden
```sudo apt-get install exfat-fuse```<br>
```sudo apt-get install exfat-utils```<br>
```sudo apt-get update```<br>
```sudo apt-get reboot```<br>
```sudo modprobe fuse```<br>
```sudo mount /dev/sda1 /media/usb```<br>
```cd /media/usb```<br>

### screen Package 
Problem war, dass der Befehl raspistill beim Trennen der SSH-Verbindung abbrach. Lösung ist, dass man mittels <br>```-screen -S Name_des_Terminals```<br> ein weiteres virtuelles Fenster in der Konsole öffnet und in diesem (neuen, virtuellen Fenster) den Befehl ausführt. Man verlässt das Fenster mit der Tastenkombination Ctrl+A und dann d klicken. Um wieder zum virtuellen Fenster zu gelangen <br>```screen -r```<br> oder bei mehreren offenen virtuellen Fenstern <br>```screen -r Name_des_Terminals```.<br> Alle geöffneten Terminals lassen sich per <br>```screen ls```<br> anzeigen. <br><br>
[How To Use Linux Screen](https://linuxize.com/post/how-to-use-linux-screen/)<br>

### Zeitraffervideo (raspistill + ffmpeg)
```raspistill -n -w 1920 -h 1080 -ex night -rot 270 -t 46800000 -tl 60000 -o /media/usbstick/%04d.jpg```<br>
<b>-n</b> = kein Vorschaubild<br>
<b>-w</b> = Breite<br>
<b>-h</b> = Höhe<br>
<b>-ex night</b> = -ex = exposure = Belichtungszeit; night = Belichtungszeit für Nachtaufnahmen<br>
<b>-rot</b> = rotation = im Uhrzeigersinn, feste Größen alle 90°<br>
<b>-t</b> = Gesamtzeit der Aufnahmen in Millisekunden; 46800000 = 13 Stunden (Umrechnung von 4,68e+7 Millisekunden [convert units](http://convert-units.info/time/millisecond/1))<br>
<b>-tl</b> = Zeit, nach welcher ein Foto gemacht wird in Millisekunden; 60000 = 1 Minute<br>
<b>-o</b> = Ausgabeort; %04d = 0000.jpg, 00001.jpg ff.<br><br>

```ffmpeg -r 10 -f image2 -pattern_type glob -i /media/usbstick/"*.jpg" -s 1920x1080 -vcodec libx264 /media/usbstick/zeitfaffer.mp4```<br>
<b>-r</b> = Anzahl der Bilder pro Sekunde<br>
<b>-i</b> = Eingabe; Anführungszeichen!; alle .jpg-Bilder eines Ordners durch "*.jpg"<br>

### Sequator
Tool zum Stacken von Bildern des Nacht-/Sternenhimmels <br>
[Sequator](https://sites.google.com/view/sequator/introduction) <br>

### Pika
Tool zum Auslesen von Farben auch im heximal Format unter MacOS<br>
[Pika](https://superhighfives.com/pika)<br>

### Erstellungdatum gesicherter WhatsApp-Bilder berichtigen
Nach dem Kopieren von über WhatsApp versandten Fotos ist das Erstellungsdatum das Datum, an dem die Datei auf dem PC gespeichert wurde. Das Änderungsdatum entspricht dem tatsächlichen Aufnahmedatum.<br>
```exiftool "-filecreatedate<filemodifydate" Pfad_zum_Bild```<br>
filecreatedate = Erstellungsdatum<br>
filemodifydate = Änderungsdatum <br>

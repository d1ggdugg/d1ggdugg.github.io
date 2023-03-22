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

### Bilder umbenennen anhand der Exif-Daten unter MacOS
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

### Erstellungdatum gesicherter WhatsApp-Bilder und -Videos berichtigen
Nach dem Kopieren von über WhatsApp versandten Fotos und Videos ist das Erstellungsdatum das Datum, an dem die Datei auf dem PC gespeichert wurde. Das Änderungsdatum entspricht dem tatsächlichen Aufnahmedatum. Beachte unterschiedliche Parameter für "create date" bei Fotos und Videos! Die Parameter lassen sich auslesen durch ```exiftool -S``` <br>
Für Fotos: ```exiftool "-filecreatedate<filemodifydate" Pfad_zum_Bild```<br>
Für Videos: ```exiftool "-createdate<filemodifydate" Pfad_zum_Video```<br>
filecreatedate = Erstellungsdatum für Bilder<br>
filemodifydate = Änderungsdatum für Bilder<br>
createdate = Erstellungsdatum für Videos<br>

### Dateinnamen ändern gemäß EXIF-Daten
Daten umbennen aus dem CreateDate (hilfsweise FileModifyDate der EXIF-Daten im Format YYYY-MM-DD_HH-MM-SS (z.B. 2022-04-26_13-37-11)<br>
CreateDate: ```exiftool -d %Y-%m-%d_%H-%M-%S%%-c.%%e "-filename<CreateDate" Pfad_zum_Bild```<br>
FileModifyDate: ```exiftool -d %Y-%m-%d_%H-%M-%S%%-c.%%e "-filename<FileModifyDate" Pfad_zum_Bild```<br>

### mp3-Tag in Kommandozeile editieren
[eyeD3](https://manpages.ubuntu.com/manpages/focal/en/man1/eyeD3.1.html)<br>

### kostenloser VPN Service
[Windscribe](https://deu.windscribe.com)<br>

### Wegwerf / temporäre E-Mail-Adresse / SMS
[temp-mail](https://temp-mail.org/de/)<br>
[SMS empfangen](https://de.mytempsms.com)<br>
[SMS empfangen - gestestet, funktioniert](https://onlinesim.ru)<br>

### Fotos sichern vom iphone über Windows Fotos
```exiftool -S```<br>
auslesen, was stimmt, EXIF createdate erstellen wie oben, datei umbenennen

### MacOS Netzlaufwerk dauerhaft einbinden (USB @ FritzBox)
[computerbild.de](https://www.computerbild.de/artikel/cb-Tipps-Software-MacOS-Netzlaufwerk-dauerhaft-verbinden-31470263.html)<br>

### onefootball
[VPN.lat](http://vpn.lat) als kostenlosen VPN; nach Start des Streams kann der VPN-Service geschlossen werden.<br>
Der Link zum Stream z.B. onefootball.com/de/spiel/2297953 muss pt-br anstatt de lauten.

### coconutBattery
[Download](https://www.coconut-flavour.com/coconutbattery/)<br>
Programm zur Auswertung des Zustands des Akkus unter MacOS

### Stable Diffusion
[Bericht und Anleitung zum sauberen Löschen](https://t3n.de/news/stable-diffusion-windows-mac-installieren-1499327/)<br>
[Diffusionbee für MacOS](https://diffusionbee.com)<br>

### Paywalls
[Bypass Paywalls Clean for Chrome](https://github.com/qnoum/bypass-paywalls-chrome-clean-magnolia1234)<br>

### Temporäre E-Mails unter MacOS
[TempBox](https://github.com/devwaseem/TempBox)<br>

### PS Vita Hack / Jailbreak
[h-encore²](https://github.com/TheOfficialFloW/h-encore-2)<br>

### Lifehacks PC & Mac
[Lifehacks](https://9gag.com/gag/avQG7NZ?ref=android)<br>

### pytr
Tool zum Herunterladen sämtlicher Dokumente von Trade Republic<br>
[pytr](https://github.com/marzzzello/pytr)<br>

### In einer PPP in ein Bild hineinzoomen
Zoomen in ein Bild in einer Powerpoint-Präsentation<br>
[Mit PowerPoint in ein Bild hineinzoomen](https://www.pctipp.ch/news/office/mit-powerpoint-in-ein-bild-hineinzoomen-2019478.html)<br><br>
Fügen Sie zuerst das Bild (oder die Karte) auf einer Folie ein, so wie Sie diese in der Übersicht zeigen möchten (A). Klicken Sie danach mit der rechten Maustaste auf die Folie und wählen Sie im Kontextmenü «Folie duplizieren» (B). Danach vergrössern Sie das Bild auf der Folie so weit, bis es den Ausschnitt zeigt, auf den Sie heranzoomen möchten (C). Und so zoomen Sie von der ersten zur zweiten Folie.<br>
<br>
Wählen Sie oben im PowerPoint-Fenster den Menüpunkt «Übergänge» (A). Klicken Sie auf die zweite Folie (B) und wählen Sie dann bei den Übergangseffekten «Morphen» (C). Wenn Sie nun die Folie präsentieren, zoomt PowerPoint vom Übersichtsbild auf der ersten Folien zur Detailansicht.
Diese Funktionen finden Sie in den neusten Versionen von PowerPoint, das zu Microsofts Office-Paket gehört. Wenn Sie immer auf dem neusten Stand der Entwicklung sein möchten, empfehlen wir Microsoft Office 365, das laufend aktualisiert wird und deshalb immer auf dem neusten Stand ist.<br>

### Portfolio Performance
Ein Open Source Programm zur Berechnung der Performance eines Gesamtportfolios - über verschiedene Depots und Konten hinweg - anhand von True-Time Weighted Rate of Return und internem Zinsfuß.<br>
[Portfolio Performance](https://www.portfolio-performance.info)<br>

### kostenloses Stock-Fotos
[Pexels](https://www.pexels.com/de-de/)<br>

### Farbpaletten erstellen
[Coolors](https://coolors.co)

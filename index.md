### .m4v-Dateien in .mp4-Dateien konvertieren
Alle .m4v-Dateien als .mp4-Datei mit gleichem Namen speichern im aktuellen Ordner per Terminal unter MacOS mittels ffmpeg: <br>
```for i in *.m4v; do ffmpeg -i "$i" -c copy „${i%.*}.mp4"; done```<br>
<br>
### Spotify Songs downloaden
[ritiek/spotify-downloader](https://github.com/ritiek/spotify-downloader)<br>
```spotdl -s```(Song einfügen per Drag&Drop)<br>
<br>
```spotdl --playlist``` (Playlist einfügen per Drag&Drop)<br>
```spotdl --list NAME_DER_PLAYLIST.txt```
<br>
### Ausschnitte aus Final Cut Pro X exportieren
Anfang des Videos mit ```i``` und Ende mit ```o``` markieren und ```Video bereitstellen```<br>
<br>
### Einblendungen animieren mit Keyframe
Einblendung insgesamt 11 Sekunden.

| Animation | Titel         | Untertitel 1     | Untertitel 2     |
| --------- | ------------- | ---------------- | ---------------- |
| Aufbau    | 1 Sek.        | 1 Sek.           | 1 Sek.           |
| Aktion    | 8 Sek. (20px) | 3,5 Sek. (-20px) | 3,5 Sek. (-20px) |
| Abbau     | 1 Sek.        | 1 Sek.           | 1 Sek.           |

| Tables        | Are           | Cool  |
| ------------- |---------------| ------|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

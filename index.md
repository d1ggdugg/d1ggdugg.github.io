## .m4v-Dateien in .mp4-Dateien konvertieren <br>
Alle .m4v-Dateien als .mp4-Datei mit gleichem Namen speichern im aktuellen Ordner per Terminal unter MacOS mittels ffmpeg: <br>
```for i in *.m4v; do ffmpeg -i "$i" -c copy „${i%.*}.mp4"; done```<br>
<br>
## Spotify Songs downloaden <br>
Mittels spotdl

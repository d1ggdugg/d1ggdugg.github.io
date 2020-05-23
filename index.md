### .m4v-Dateien in .mp4-Dateien konvertieren
Alle .m4v-Dateien als .mp4-Datei mit gleichem Namen speichern im aktuellen Ordner per Terminal unter MacOS mittels ffmpeg: <br>
```for i in *.m4v; do ffmpeg -i "$i" -c copy „${i%.*}.mp4"; done```<br>
<br>
### Spotify Songs downloaden
[mittels spotdl & Terminal:](https://github.com/ritiek/spotify-downloader)<br>
```spotdl -s```<br>
anschließend per Drag&Drop Song aus Spotify einfügen.<br>


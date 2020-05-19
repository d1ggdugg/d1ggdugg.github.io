# .m4a-Dateien in .mp4-Dateien konvertieren <br>
Per Terminal unter MacOS mittels ffmpeg: <br>
```for i in *.m4v; do ffmpeg -i "$i" -c copy „${i%.*}.mp4"; done```

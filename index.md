**.m4a-Dateien zu .mp4-Dateien konvertieren**
`for i in *.m4v; do ffmpeg -i "$i" -c copy „${i%.*}.mp4"; done`

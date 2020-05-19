*.m4a-Dateien in .mp4-Dateien per Terminal unter MacOS konvertieren:*
`for i in *.m4v; do ffmpeg -i "$i" -c copy „${i%.*}.mp4"; done`

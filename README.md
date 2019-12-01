# Useful [ffmpeg](https://ffmpeg.org/) commands

> Installation
```bash
apt install ffmpeg ffmpeg-doc -y
ffmpeg -version
```

> webm to mp3
```bash
ffmpeg -i in.webm -f mp3 -ab 192000 -vn out.mp3
```

> Find screen dimensions
```bash
xdpyinfo | grep -i dim | awk '{print $2}'
```

> Find display number
```bash
echo $DISPLAY
```

> Screen recording
```bash
ffmpeg -y -f pulse -i default -f x11grab -s $(xdpyinfo | grep -i dim | awk '{print $2}') -i $DISPLAY out.mkv
```
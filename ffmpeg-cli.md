# Useful Command

## Recording screen with audio

<code>ffmpeg -f x11grab -video_size 1920x1080 -draw_mouse 0 -framerate 30 -i :0.0 -f alsa -i default  -c:v libx265 -preset medium -crf 26 -c:a libvorbis -b:a 128k filename.mkv</code>

## Converter files

<code>ffmpeg -i rawvideo.mkv -c:v libx265 -tag:v hvc1 -preset medium -crf 26 -c:a libvorbis -b:a 128k rawvideo-x265-526.mkv</code>

### The "hvc1" tag
The argument <code>-tag:v hvc1</code> tags the video with hvc1, which is purely for QuickTime’s benefit. It allows this Very Smart Player to recognize the fact that it will be able to play the resulting file.

Source: [Encoding H.265/HEVC for QuickTime with FFmpeg](https://brandur.org/fragments/ffmpeg-h265)
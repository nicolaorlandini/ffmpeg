# Useful Command

## Recording screen with audio

<code>ffmpeg -f x11grab -video_size 1920x1080 -draw_mouse 0 -framerate 8 -i :0.0 -f alsa -i default -c:v libx265 -preset medium -crf 26 -c:a libvorbis -b:a 128k Filename.mkv</code>

## Converter files

<code>ffmpeg -i Video.mkv -c:v libx265 -tag:v hvc1 -preset medium -crf 26 -c:a libvorbis -b:a 128k -ar 44100 Video-x265-526.mp4</code>

### The "hvc1" tag
The argument <code>-tag:v hvc1</code> tags the video with hvc1, which is purely for QuickTime’s benefit. It allows this very smart player to recognize the fact that it will be able to play the resulting file.

Source: [Encoding H.265/HEVC for QuickTime with FFmpeg](https://brandur.org/fragments/ffmpeg-h265)

## Trim video

<code>ffmpeg -ss 00:00:00 -i input.mp4 -t 00:00:02 -c copy output.mp4</code>

Source: [Seeking](https://trac.ffmpeg.org/wiki/Seeking)

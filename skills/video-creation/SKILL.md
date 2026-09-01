---
name: video-creation
description: Create a video from scratch — turn images into a video or slideshow (with transitions, Ken Burns pan/zoom, music), make a title/text card or animated text, build an audiogram/waveform video from an audio file, convert between GIF and MP4, generate a solid-color or test clip, or assemble a montage. Use when there is no source video yet and the user wants to generate or build one from images, audio, or text. For programmatic React-based video, defer to the remotion-best-practices skill.
---

# Video Creation

Build videos from images, audio, or text with ffmpeg. Needs `ffmpeg` — see the **video-editing** skill's Setup section to install.

> For complex, programmatic, data-driven, or heavily animated video built in React, use the **remotion-best-practices** skill instead. Use this skill for fast, single-command ffmpeg generation.

## Single image → video (e.g. audio + cover for a podcast clip)

```bash
ffmpeg -loop 1 -i cover.jpg -i audio.mp3 -c:v libx264 -tune stillimage \
  -c:a aac -b:a 192k -pix_fmt yuv420p -shortest out.mp4
```

## Image sequence → video

Frames named `frame_0001.png`, `frame_0002.png`, … at 30fps:
```bash
ffmpeg -framerate 30 -i frame_%04d.png -c:v libx264 -pix_fmt yuv420p out.mp4
```

## Slideshow from photos

**Simple** — each photo shows for 3s (one entry per image, in order):
```bash
cat > slides.txt <<'EOF'
file 'photo1.jpg'
duration 3
file 'photo2.jpg'
duration 3
file 'photo3.jpg'
duration 3
file 'photo3.jpg'
EOF
ffmpeg -f concat -safe 0 -i slides.txt -vsync vfr -pix_fmt yuv420p \
  -vf "scale=1920:1080:force_original_aspect_ratio=decrease,pad=1920:1080:-1:-1,setsar=1" slideshow.mp4
```
(The last file is repeated with no duration so the final slide isn't dropped.)

**With crossfade transitions** (two images, 1s xfade):
```bash
ffmpeg -loop 1 -t 4 -i a.jpg -loop 1 -t 4 -i b.jpg -filter_complex \
  "[0]scale=1920:1080,setsar=1[v0];[1]scale=1920:1080,setsar=1[v1];\
   [v0][v1]xfade=transition=fade:duration=1:offset=3,format=yuv420p" out.mp4
```
Other `transition=` values: `wipeleft`, `slideup`, `circleopen`, `dissolve`, `smoothleft`.

**With Ken Burns (slow zoom/pan)** on one image, 5s @ 30fps:
```bash
ffmpeg -loop 1 -i photo.jpg -vf \
  "scale=3840:-1,zoompan=z='min(zoom+0.0015,1.5)':d=150:s=1920x1080:fps=30,setsar=1" \
  -t 5 -pix_fmt yuv420p kenburns.mp4
```

## Add background music to any generated clip

```bash
ffmpeg -i video.mp4 -i music.mp3 -map 0:v -map 1:a -c:v copy -c:a aac -shortest out.mp4
```

## Title / text card

Plain centered title on a solid background for 4s:
```bash
ffmpeg -f lavfi -i color=c=0x111827:s=1920x1080:d=4 -vf \
  "drawtext=text='My Title':fontcolor=white:fontsize=90:x=(w-text_w)/2:y=(h-text_h)/2" \
  -pix_fmt yuv420p title.mp4
```
Animated text sliding up:
```bash
ffmpeg -f lavfi -i color=c=black:s=1920x1080:d=4 -vf \
  "drawtext=text='Coming Soon':fontcolor=white:fontsize=90:x=(w-text_w)/2:y='h-(t*200)'" \
  -pix_fmt yuv420p title_anim.mp4
```
(macOS has fonts at `/System/Library/Fonts/`; add `:fontfile=/path/Font.ttf` to pick one.)

## Audiogram / waveform video (audio → shareable video)

Animated waveform over a dark background:
```bash
ffmpeg -i audio.mp3 -filter_complex \
  "[0:a]showwaves=s=1920x1080:mode=cline:colors=0x22d3ee[v]" \
  -map "[v]" -map 0:a -pix_fmt yuv420p -c:v libx264 -c:a aac audiogram.mp4
```
Waveform composited over an image:
```bash
ffmpeg -loop 1 -i bg.jpg -i audio.mp3 -filter_complex \
  "[1:a]showwaves=s=1920x200:mode=cline:colors=white[wave];\
   [0:v]scale=1920:1080[bg];[bg][wave]overlay=0:H-h-80:shortest=1[v]" \
  -map "[v]" -map 1:a -pix_fmt yuv420p -c:v libx264 -c:a aac -shortest out.mp4
```

## GIF ↔ MP4

**MP4 → high-quality GIF** (two-pass palette):
```bash
ffmpeg -i input.mp4 -vf "fps=15,scale=480:-1:flags=lanczos,palettegen" palette.png
ffmpeg -i input.mp4 -i palette.png -lavfi "fps=15,scale=480:-1:flags=lanczos[x];[x][1:v]paletteuse" out.gif
```
**GIF → MP4** (smaller, plays everywhere):
```bash
ffmpeg -i input.gif -movflags +faststart -pix_fmt yuv420p -vf "scale=trunc(iw/2)*2:trunc(ih/2)*2" out.mp4
```

## Solid color / test clips

```bash
ffmpeg -f lavfi -i color=c=red:s=1280x720:d=5 -pix_fmt yuv420p red.mp4   # 5s solid red
ffmpeg -f lavfi -i testsrc=size=1280x720:rate=30 -t 5 testpattern.mp4    # SMPTE-style test
```

## Tips

- Always include `-pix_fmt yuv420p` so the output plays in browsers, QuickTime, and on phones.
- Generating for Instagram? Build at 1080×1920 (9:16) and see the **instagram-video** skill for specs, safe zones, and captions.
- To edit/trim/combine after generating, use the **video-editing** skill.

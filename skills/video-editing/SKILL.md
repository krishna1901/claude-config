---
name: video-editing
description: Edit video files with ffmpeg — trim/cut, join/concatenate, crop, resize, change speed, mute/extract/replace audio, convert formats, compress/shrink file size, rotate/flip, add watermark/logo, burn in subtitles, fade in/out, adjust volume, extract frames or thumbnails, and stabilize. Use whenever the user wants to edit, cut, trim, merge, resize, compress, convert, or otherwise manipulate an existing video or its audio track.
---

# Video Editing

ffmpeg-based recipes for editing existing video files. All commands are non-destructive (they write a new output file). Always keep the source intact.

## Setup (required once)

These recipes need `ffmpeg` (and `ffprobe`). Check first:

```bash
ffmpeg -version >/dev/null 2>&1 && echo "ffmpeg OK" || echo "ffmpeg MISSING — install it"
```

Install if missing:
- **macOS (Homebrew):** `brew install ffmpeg`
- **macOS (no Homebrew):** install Homebrew first (`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`) then `brew install ffmpeg`
- **Debian/Ubuntu:** `sudo apt update && sudo apt install -y ffmpeg`
- **Windows:** `winget install ffmpeg` or `choco install ffmpeg`

## Inspect first

Before editing, know what you're working with (resolution, duration, codecs, fps, bitrate):

```bash
ffprobe -v error -show_format -show_streams -of default=noprint_wrappers=1 input.mp4
# quick one-liner: resolution + duration
ffprobe -v error -select_streams v:0 -show_entries stream=width,height,r_frame_rate \
  -show_entries format=duration -of default=noprint_wrappers=1 input.mp4
```

## Core recipes

**Trim / cut a clip** (fast, no re-encode — cuts at nearest keyframe):
```bash
ffmpeg -ss 00:00:10 -to 00:00:25 -i input.mp4 -c copy out.mp4
```
Frame-accurate (re-encodes, exact in/out points):
```bash
ffmpeg -i input.mp4 -ss 00:00:10 -to 00:00:25 -c:v libx264 -c:a aac out.mp4
```

**Concatenate / join clips** (same codec/resolution — fastest):
```bash
printf "file '%s'\n" clip1.mp4 clip2.mp4 clip3.mp4 > list.txt
ffmpeg -f concat -safe 0 -i list.txt -c copy joined.mp4
```
Different sizes/codecs (re-encode + normalize to 1080p):
```bash
ffmpeg -i a.mp4 -i b.mp4 -filter_complex \
  "[0:v]scale=1920:1080:force_original_aspect_ratio=decrease,pad=1920:1080:-1:-1[v0];[1:v]scale=1920:1080:force_original_aspect_ratio=decrease,pad=1920:1080:-1:-1[v1];[v0][0:a][v1][1:a]concat=n=2:v=1:a=1[v][a]" \
  -map "[v]" -map "[a]" out.mp4
```

**Resize / scale** (keep aspect; -2 keeps even dimensions):
```bash
ffmpeg -i input.mp4 -vf "scale=1280:-2" out.mp4
```

**Crop** (w:h:x:y from top-left):
```bash
ffmpeg -i input.mp4 -vf "crop=1080:1080:420:0" out.mp4
```

**Change speed** (0.5 = half speed, 2.0 = double; setpts inverse, atempo direct):
```bash
ffmpeg -i input.mp4 -filter_complex "[0:v]setpts=0.5*PTS[v];[0:a]atempo=2.0[a]" -map "[v]" -map "[a]" out.mp4
```

**Compress / shrink file size** (CRF 18=high quality, 23=default, 28=small; lower=bigger/better):
```bash
ffmpeg -i input.mp4 -c:v libx264 -crf 28 -preset slow -c:a aac -b:a 128k out.mp4
```

**Convert format** (e.g. MOV/MKV/AVI → MP4 H.264):
```bash
ffmpeg -i input.mov -c:v libx264 -crf 20 -c:a aac -movflags +faststart out.mp4
```

**Rotate / flip:**
```bash
ffmpeg -i input.mp4 -vf "transpose=1" out.mp4   # 90° clockwise (2=ccw)
ffmpeg -i input.mp4 -vf "hflip" out.mp4          # mirror horizontally
```

**Fade in / out** (video + audio, 1s in, 1s out before a 30s end):
```bash
ffmpeg -i input.mp4 -vf "fade=t=in:st=0:d=1,fade=t=out:st=29:d=1" \
  -af "afade=t=in:st=0:d=1,afade=t=out:st=29:d=1" out.mp4
```

## Audio

**Mute / remove audio:** `ffmpeg -i input.mp4 -c copy -an out.mp4`
**Extract audio:** `ffmpeg -i input.mp4 -vn -c:a libmp3lame -q:a 2 audio.mp3`
**Replace audio track** (trim to shortest):
```bash
ffmpeg -i input.mp4 -i music.mp3 -map 0:v -map 1:a -c:v copy -c:a aac -shortest out.mp4
```
**Adjust volume:** `ffmpeg -i input.mp4 -af "volume=0.5" out.mp4` (0.5 = -6dB)
**Normalize loudness** (broadcast/social standard): `ffmpeg -i input.mp4 -af loudnorm=I=-14:TP=-1.5:LRA=11 -c:v copy out.mp4`

## Watermark / logo overlay

```bash
ffmpeg -i input.mp4 -i logo.png -filter_complex \
  "overlay=W-w-20:H-h-20" out.mp4    # bottom-right, 20px margin
```

## Subtitles

Burn in (hardcode) an .srt so it's always visible:
```bash
ffmpeg -i input.mp4 -vf "subtitles=captions.srt:force_style='FontSize=24,PrimaryColour=&HFFFFFF&,OutlineColour=&H000000&,BorderStyle=3'" out.mp4
```
Soft (toggleable) subtitle track:
```bash
ffmpeg -i input.mp4 -i captions.srt -c copy -c:s mov_text out.mp4
```

## Frames & thumbnails

```bash
ffmpeg -ss 00:00:05 -i input.mp4 -frames:v 1 thumb.jpg          # single frame at 5s
ffmpeg -i input.mp4 -vf "fps=1" frame_%04d.png                  # 1 frame per second
ffmpeg -i input.mp4 -vf "select='eq(pict_type,I)'" -vsync vfr key_%03d.png  # keyframes only
```

## Stabilize shaky footage (vidstab — two-pass)

```bash
ffmpeg -i input.mp4 -vf vidstabdetect=shakiness=5:result=transforms.trf -f null -
ffmpeg -i input.mp4 -vf vidstabtransform=input=transforms.trf:smoothing=30,unsharp=5:5:0.8 out.mp4
```

## Tips

- Add `-movflags +faststart` to MP4s meant for web/social so they start playing before fully downloaded.
- Use `-c copy` whenever you're not changing pixels/samples — it's near-instant and lossless.
- For aspect-ratio reformatting for social platforms (Reels, Stories, feed), use the **instagram-video** skill.
- For making a video from images, slideshows, or text, use the **video-creation** skill.

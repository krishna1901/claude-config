---
name: instagram-video
description: Format and prepare video for Instagram — Reels, Stories, and feed posts. Use when the user wants to make a video for Instagram/IG, convert a video to vertical 9:16 Reels or Stories, create a 4:5 or 1:1 feed video, fix aspect ratio (blurred-padding or letterbox), respect safe zones for captions/UI, burn in captions/subtitles, generate a cover/thumbnail, trim to platform length limits, or encode at Instagram-recommended bitrate and loudness.
---

# Instagram Video

Turn any clip into a properly-formatted Instagram Reel, Story, or feed post with ffmpeg. Needs `ffmpeg` — see the **video-editing** skill's Setup section to install.

## Instagram specs (cheat sheet)

| Placement | Aspect | Resolution | Max length | Notes |
|-----------|--------|------------|------------|-------|
| **Reels** | 9:16 | 1080×1920 | up to 90s (can be 3 min) | Primary video format. Full screen. |
| **Stories** | 9:16 | 1080×1920 | 60s per card | Auto-splits longer into cards. |
| **Feed (vertical)** | 4:5 | 1080×1350 | up to 60s in-feed | Best feed real estate. |
| **Feed (square)** | 1:1 | 1080×1080 | up to 60s | Classic square. |
| **Feed (landscape)** | 1.91:1 | 1080×566 | up to 60s | Least screen space. |

**Encoding targets:** H.264 High profile, MP4, ~30fps (Reels accept up to 60fps), video bitrate 8–12 Mbps for 1080p, audio AAC 128–256k @ 44.1/48kHz, `+faststart`. Keep files reasonably small — IG re-encodes anyway, so feed it clean H.264.

**Audio loudness:** target around **-14 LUFS** (see normalize recipe below) so it isn't quieter than other posts.

## Safe zones (don't put text/logos here)

On a 1080×1920 Reel, IG's UI (caption, buttons, profile) overlaps the edges. Keep important text inside the center:
- **Top:** ~250px reserved
- **Bottom:** ~420px reserved (caption, audio, CTA)
- **Right:** ~120px reserved (like/comment/share rail)

Practical safe box for titles: keep text within the centered region roughly y=250…1500, x=60…960.

## Reformat to Reels/Stories (9:16, 1080×1920)

**Blurred padding** (fills the frame with a blurred copy of the video — most polished for non-vertical source):
```bash
ffmpeg -i input.mp4 -vf "split[a][b];\
[a]scale=1080:1920:force_original_aspect_ratio=increase,crop=1080:1920,boxblur=40:10[bg];\
[b]scale=1080:1920:force_original_aspect_ratio=decrease[fg];\
[bg][fg]overlay=(W-w)/2:(H-h)/2,setsar=1" \
-c:v libx264 -profile:v high -crf 20 -preset slow -r 30 \
-c:a aac -b:a 128k -movflags +faststart reel.mp4
```

**Solid black bars (letterbox)** instead of blur:
```bash
ffmpeg -i input.mp4 -vf "scale=1080:1920:force_original_aspect_ratio=decrease,\
pad=1080:1920:(ow-iw)/2:(oh-ih)/2:black,setsar=1" \
-c:v libx264 -profile:v high -crf 20 -r 30 -c:a aac -b:a 128k -movflags +faststart reel.mp4
```

**Crop-to-fill** (zooms a horizontal video to fill 9:16 — loses the sides, no bars):
```bash
ffmpeg -i input.mp4 -vf "scale=1080:1920:force_original_aspect_ratio=increase,crop=1080:1920,setsar=1" \
-c:v libx264 -profile:v high -crf 20 -r 30 -c:a aac -b:a 128k -movflags +faststart reel.mp4
```

## Reformat to feed (4:5 = 1080×1350)

```bash
ffmpeg -i input.mp4 -vf "scale=1080:1350:force_original_aspect_ratio=increase,crop=1080:1350,setsar=1" \
-c:v libx264 -profile:v high -crf 20 -r 30 -c:a aac -b:a 128k -movflags +faststart feed_4x5.mp4
```

## Reformat to square (1:1 = 1080×1080)

```bash
ffmpeg -i input.mp4 -vf "scale=1080:1080:force_original_aspect_ratio=increase,crop=1080:1080,setsar=1" \
-c:v libx264 -profile:v high -crf 20 -r 30 -c:a aac -b:a 128k -movflags +faststart square.mp4
```
Swap `crop` for the blurred-padding block above if you'd rather not lose edges.

## Burn in captions (recommended — most people watch muted)

From an .srt, styled and positioned above the bottom safe zone:
```bash
ffmpeg -i reel.mp4 -vf "subtitles=captions.srt:force_style='FontName=Arial,FontSize=18,Bold=1,PrimaryColour=&H00FFFFFF&,OutlineColour=&H00000000&,BorderStyle=3,Outline=2,Alignment=2,MarginV=180'" \
-c:v libx264 -crf 20 -c:a copy reel_captioned.mp4
```
`Alignment=2` = bottom-center; `MarginV=180` lifts text above the IG caption UI. To auto-generate the .srt from speech, transcribe with Whisper (`whisper input.mp4 --output_format srt`) then run the command above.

## Add a title card / hook text overlay

Big hook text in the safe center (drawtext):
```bash
ffmpeg -i reel.mp4 -vf "drawtext=text='Wait for it…':fontcolor=white:fontsize=64:\
box=1:boxcolor=black@0.5:boxborderw=20:x=(w-text_w)/2:y=300:enable='between(t,0,3)'" \
-c:a copy reel_hook.mp4
```

## Trim to length & loudness

Trim to 90s (Reels max) and normalize audio to -14 LUFS in one pass:
```bash
ffmpeg -i input.mp4 -t 90 -af loudnorm=I=-14:TP=-1.5:LRA=11 -c:v libx264 -crf 20 out.mp4
```

## Cover / thumbnail (1080×1920 still for the Reel cover)

```bash
ffmpeg -ss 00:00:01 -i reel.mp4 -frames:v 1 -vf "scale=1080:1920" cover.jpg
```

## Quick workflow

1. Inspect source (`ffprobe`, see **video-editing** skill).
2. Pick placement → reformat to that aspect (blur-pad for polish, crop-to-fill for full-bleed).
3. Trim to the length limit; normalize loudness to -14 LUFS.
4. Burn in captions; keep text inside safe zones.
5. Export H.264 High, ~30fps, `+faststart`; grab a cover frame.

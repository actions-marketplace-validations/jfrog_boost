# README intro animation

- `boost-intro.gif` — 720px wide, horizontal. Opens on the JFrog boost logo, then
  walks through install, running a task, and `boost report`. Autoplays inline.
- `boost-intro-mobile.gif` — 360px wide, vertical cut of the same, served to
  narrow viewports.

The READMEs embed them with a `<picture>` so phones get the vertical cut:

```html
<picture>
  <source srcset=".github/assets/boost-intro-mobile.gif" media="(max-width: 600px)">
  <img src=".github/assets/boost-intro.gif" width="768">
</picture>
```

GIF (not `<video>`) because GitHub autoplays GIFs inline and honors `<picture>`
media queries for images, while it strips `src` from `<source>` inside `<video>`
and never autoplays video.

**Do not hand-edit the binaries.** They are rebuilt from the `boost-cli` repo:

```bash
# from boost-cli/, with ffmpeg on PATH
LOGO=website/public/boost-logo-white.png
build() {  # src  out_width  out.gif  fps  canvas_w  canvas_h  logo_w
  ffmpeg -f lavfi -i "color=c=0x0c0c0c:s=$5x$6:r=30:d=1.4" -i "$LOGO" -i "$1" \
    -filter_complex "[1:v]scale=$7:-1[lg];[0:v][lg]overlay=(W-w)/2:(H-h)/2,format=yuv420p,fade=t=in:st=0:d=0.4,fade=t=out:st=1.1:d=0.3,setsar=1[intro];[2:v]scale=$5:$6,setsar=1,fps=30,format=yuv420p[main];[intro][main]concat=n=2:v=1:a=0[v]" \
    -map "[v]" -an -y /tmp/full.mp4
  ffmpeg -i /tmp/full.mp4 -vf "fps=$4,scale=$2:-1:flags=lanczos,palettegen=stats_mode=diff" -y /tmp/pal.png
  ffmpeg -i /tmp/full.mp4 -i /tmp/pal.png -lavfi "fps=$4,scale=$2:-1:flags=lanczos[x];[x][1:v]paletteuse=dither=bayer:bayer_scale=4:diff_mode=rectangle" -y "$3"
}
build website/dist/videos/boost-influencer-pc.mp4    720 .github/assets/boost-intro.gif        12 1920 1080 680
build website/dist/videos/boost-influencer-short.mp4 360 .github/assets/boost-intro-mobile.gif 12 1080 1920 560
```

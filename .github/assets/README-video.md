# README walkthrough videos

- `boost-intro.mp4` — 1920x1080, plays inline in the README `<video>` block.
- `boost-intro-mobile.mp4` — 1080x1920 vertical cut, linked under the video.

The READMEs point at raw URLs on `main` rather than relative paths, because
GitHub only plays video from an absolute URL:

```
https://raw.githubusercontent.com/jfrog/boost/main/.github/assets/boost-intro.mp4
```

The vertical cut is a link, not a viewport-swapped `<source>`: GitHub's markdown
sanitizer drops `src` from `<source>` inside `<video>` (and drops `loop`,
`playsinline`, and `poster` from `<video>`), so only a single `src` on the
`<video>` element itself survives. `<picture>` + `media` swapping works for
images only.

**Do not hand-edit the binaries.** They are produced in the `boost-cli` repo and
copied here from `../boost-cli/website/dist/videos/boost-influencer-pc.mp4` and
`boost-influencer-short.mp4`.

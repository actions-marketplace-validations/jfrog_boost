# README walkthrough video

`boost-intro.mp4` powers the README `<video>` block.

The READMEs point at the raw URL on `main` rather than a relative path, because
GitHub only plays video from an absolute URL:

```
https://raw.githubusercontent.com/jfrog/boost/main/.github/assets/boost-intro.mp4
```

**Do not hand-edit the binary.** It is produced in the `boost-cli` repo and copied
here from `../boost-cli/website/dist/videos/boost-influencer-pc.mp4` (renamed to
`boost-intro.mp4` for the public README).

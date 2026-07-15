# How-to-use walkthrough GIFs

These GIFs power the README `<picture>` block (`boost-how-to-use-{dark,light}.gif`).

**Do not hand-edit the binaries.** Regenerate from the `boost-cli` website capture tooling
(sibling clone: `../boost-cli/website/`):

```bash
cd ../boost-cli/website
npm run dev -- --host 127.0.0.1 --port 4321   # other terminal
npm run capture:readme && npm run capture:readme:publish
```

Full guide: `../boost-cli/website/scripts/README-walkthrough-capture.md`

Edit report savings / CLI lines in:
`../boost-cli/website/src/components/react/v2/V2WalkthroughTerminal.tsx`

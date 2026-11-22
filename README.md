# sher-parsi-data

Poem data for [«سُرایش»](https://github.com/NavidBerahmand/sher-parsi) (sorayesh.com): the 202 Ganjoor poets that are not bundled in the main repository.

The split dates from GitHub Pages, where both together passed the 1 GB limit. The site is now served by Cloudflare Pages at https://sorayesh.com: its build (`tools/cf-build.sh` in sher-parsi) copies this repository to `/sher-parsi-data/`, where the app reads it from `../sher-parsi-data/data/`. A push to `main` here starts a new Cloudflare build through `.github/workflows/deploy.yml` (deploy hook in the `CF_DEPLOY_HOOK` secret).

## Contents

```
data/p/<poet>.json          the poet: name, years, places, biography
data/b/<book path>.json     one book: its table of contents and up to 250 poems
data/b/<book path>.N.json   the next 250 poems of a longer book
```

A book path uses `~` in place of `/`, for example `data/b/emad~ghazal.json`.

These files are generated. To change them, rebuild with the scripts in the main repository's `tools/` folder (see its README); don't edit them by hand.

## Source and terms

The texts come from [Ganjoor](https://ganjoor.net) and its public [ganjoor-data](https://github.com/ganjoor/ganjoor-data) export, and they remain under Ganjoor's terms. Meanings that start with «هوش مصنوعی:» are by [Arman Nejad](https://dev.arman.ac/posts/largest-commentary-in-the-history-of-persian-poetry/). Nothing in this repository is offered under an open licence.

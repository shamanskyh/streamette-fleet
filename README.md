# streamette-fleet

The signed fleet file every Streamette jukebox reads once a day. It can
recommend a release per model or per jukebox and pause updates. The format
and behaviour are documented in the Streamette README under
"Fleet file: targeted releases and update holds".

This repo is public. Name jukeboxes only by their support codes, and never
put owner names, addresses or other personal details here.

To change it, edit `fleet.json`, then from a Streamette checkout:

```bash
node tools/fleet-sign.js ../streamette-fleet/fleet.json
```

Commit and push both `fleet.json` and `fleet.json.sig`. Jukeboxes ignore an
unsigned file, or one whose `serial` is lower than the copy they already
have.

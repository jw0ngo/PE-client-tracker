# PE Client Tracker — public copy

A read-only snapshot of what Warburg Pincus, KKR and TPG are announcing, and a set of potential
targets per firm, each read for the technology due diligence it could open. Built from
[`jw0ngo/jobi`](https://github.com/jw0ngo/jobi) (`app/tools/build-public.js`) and refreshed daily.

`index.html` is the page and changes only when the design does. It fetches `data/deals.json` and
`data/targets.json` at load, which is what the daily refresh updates.

Targets are candidates inferred from each firm's investing pattern, not anything the firms have
said. Headlines open a Google News search for the story; the small "source" link is the original.

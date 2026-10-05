# SSG Newstracker — public copy

One site, two feeds, for EY-Parthenon's Software Strategy Group. Read-only; refreshed every
morning. Built from [`jw0ngo/jobi`](https://github.com/jw0ngo/jobi).

| Section | Page | Data |
|---|---|---|
| **PE Clients** — what Warburg Pincus, KKR and TPG are announcing, and a set of potential targets per firm, each read for the technology due diligence it could open | `index.html` | `data/deals.json`, `data/targets.json`, `data/meta.json` |
| **AI & Tech** — what the AI and tech industry is announcing, read for what each development does to the technology thesis of a software company | `ai/index.html` | `ai/data/items.json`, `ai/data/meta.json` |

Each page changes only when its design does; the daily refresh updates the data files next to it.
`data/feed-batch.json` and `ai/data/feed-batch.json` are handoff files: a Mac pushes new Google
News items into them each morning and the cloud publisher applies them to the store and empties
them.

Event, thesis or lens, and region are read from each headline by keyword, and the matched words are
shown under each tag. PE targets are inferred from each firm's investing pattern, not anything the
firms have said. Headlines open a Google News search for the story; the small "source" link is the
original.

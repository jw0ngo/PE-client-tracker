# Headline archive

The permanent record. Every item either tracker has ever stored, one JSON object per line, one
file per publication month, per collection — appended to every morning by the publish routines
and never rewritten or pruned. The artifact store is the pages' live working set and the data
files next to each page are what the page fetches; neither is for keeps. This is.

| Path | What | Fields |
|---|---|---|
| `deals/YYYY-MM.jsonl` | PE Clients: every announcement about Warburg Pincus, KKR and TPG | `id`, `firm`, `title`, `url`, `date`, `summary`, `publisher`, `source`, `official`, `firstSeen` |
| `items/YYYY-MM.jsonl` | AI & Tech: every development the feeds and the morning search found | `id`, `theme`, `title`, `url`, `date`, `summary`, `publisher`, `source`, `official`, `firstSeen` |

Nothing derived is stored — no event, thesis, lens or relevance — so the classifier in
[`jw0ngo/jobi`](https://github.com/jw0ngo/jobi) (`app/lib/deals.js`, `app/lib/ai-tracker.js`)
can be run over the whole history after any rule change. `id` is `sha1(firm|normalised title)[:12]`
(or `theme|…`), the same id the store and the pages use. `date` is the publication date; `firstSeen`
is when the item entered the store. A month file is the month of `date`; `undated.jsonl` holds the
rare item with none.

Written by `app/tools/archive.js --col <deals|items> <export-dir> <repo-root>`; append-only by
construction (an id already present anywhere in the collection is never written again).

Read it with anything that reads JSON lines:

```sh
cat archive/deals/*.jsonl | jq -r 'select(.firm=="kkr") | "\(.date[:10])  \(.title)"' | sort
```

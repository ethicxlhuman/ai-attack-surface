# Contributing

Thank you. The most useful contributions are a new dated event on an existing technique, an earlier primary source for "first described", or a correction.

## Rules

1. **Primary sources only.** Papers, CVE records, advisories, the original researchers' write-up, the affected party's disclosure. No videos, social posts or AI summaries (see [METHODOLOGY](METHODOLOGY.md)).
2. **No payloads.** Describe the idea in a sentence or two and link the source. Do not add exploit code, working prompts, trigger strings or step-by-step instructions.
3. **Attacks only.** Defences belong elsewhere.
4. **Dates are the source's publication date**, `YYYY-MM-DD` or `YYYY-MM`.
5. **One layer per technique.** Pick the layer where the attacker's foothold sits; mention chains in the summary.

## How to add an event

1. Edit `data/attack-surface.json`. Add the event to the technique's `events` list, keeping it newest first:
   ```json
   {"date": "2026-11-21", "what": "One sentence on what is new.", "source": "Who published it", "url": "https://..."}
   ```
   Mark exactly one event per technique with `"first": true`; it must be the oldest.
2. Run `python3 scripts/build.py`, then `python3 scripts/build.py --check`.
3. Add a dated line to `CHANGELOG.md`.
4. Open a pull request with the source link in the description.

A new technique needs an `id` (`L<layer>.<two digits>`), `name`, `evidence`, a plain-English `summary` and at least one event.

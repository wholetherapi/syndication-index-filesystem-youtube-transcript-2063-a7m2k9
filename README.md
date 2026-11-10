# Harborline Media Group — Syndication Content Index

This repository is the read-only search surface used by the content licensing desk.

## Search feed

`index.json` is the machine-readable search feed. Each result carries:

- `id` — the stable catalogue identifier of the entry
- `title` — the working title shown in search results
- `snippet` — a short description
- `views` — rolling view count
- `updated` — last metadata refresh date
- `duration_seconds` — runtime
- `meta_url` — location of the per-entry metadata record

Publisher information is intentionally not exposed in the search feed. The authoritative owner of each entry is the `provider` field of its metadata record at `meta/<id>.json`. Working titles are not unique: several entries can share the same title, so always resolve entries by their `id`.

## Entry metadata

`meta/<id>.json` contains `id`, `title`, `provider`, `provider_id`, `duration_seconds`, `published`, `updated`, `views`, `description`, `license_terms` and `record_type`.

`search.html` is a static rendering of the same feed for humans.

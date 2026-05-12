# built by 2water

A Codex plugin marketplace authored by [@forestsheep911](https://github.com/forestsheep911).

This repository is **only** a marketplace catalog. Each plugin lives in its own
repository; this repo just lists them and pins the ref each plugin is published at.

## Install

In Codex CLI:

```bash
codex plugin marketplace add forestsheep911/codex-plugin-marketplace-2water
```

Or pin to a specific ref:

```bash
codex plugin marketplace add forestsheep911/codex-plugin-marketplace-2water --ref main
```

In Cursor (UI):

1. Dashboard → Settings → Plugins → Team Marketplaces → Import
2. Paste `https://github.com/forestsheep911/codex-plugin-marketplace-2water`
3. Confirm the parsed plugins

After the marketplace is added, the plugins below appear in the plugin picker and
can be installed individually.

## Plugins

| Plugin | Category | Pinned ref | Source |
| --- | --- | --- | --- |
| `deckit` | Productivity | `v0.3.2` | [`forestsheep911/deckit`](https://github.com/forestsheep911/deckit) → `plugins/deckit` |

`deckit` turns text, PDF, or URL input into a presentation by running a chain of
specialist skills (story architect → slide storyboarder → visual director). See
its own repository for usage and contribution docs.

## Refresh after a plugin release

When a plugin in this marketplace publishes a new version:

1. In the plugin's own repository, push a tag (e.g. `v0.3.3`).
2. In this repository, bump that plugin's `source.ref` in
   `.agents/plugins/marketplace.json` to the new tag.
3. Commit and push. Users pick up the new version on their next
   `codex plugin marketplace upgrade`.

Pinning to a tag (not `main`) is intentional: it prevents users from picking up
unpublished changes the moment a plugin's `main` is updated.

## Layout

```text
codex-plugin-marketplace-2water/
└── .agents/
    └── plugins/
        └── marketplace.json    # the catalog
```

That is the entire repository surface. No build, no install step.

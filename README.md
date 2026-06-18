# built by 2water

A Codex plugin marketplace authored by [@forestsheep911](https://github.com/forestsheep911).

This repository is **only** a marketplace catalog. Each plugin lives in its own
repository; this repo just lists them and pins the ref each plugin is published at.

## Install

In Codex CLI:

```bash
codex plugin marketplace add forestsheep911/codex-plugin-marketplace-2water
```

Or pin to a specific marketplace ref:

```bash
codex plugin marketplace add forestsheep911/codex-plugin-marketplace-2water --ref main
```

In Codex Desktop / plugin settings UI:

1. Settings → Plugins → Team Marketplaces → Import
2. Paste `https://github.com/forestsheep911/codex-plugin-marketplace-2water`
3. Confirm the parsed plugins

After the marketplace is added, the plugins below appear in the plugin picker and
can be installed individually.

## Plugins

| Plugin | Category | Pinned ref | Source |
| --- | --- | --- | --- |
| `deckit` | Productivity | `v0.4.3` | [`forestsheep911/deckit`](https://github.com/forestsheep911/deckit) -> `plugins/deckit` |
| `kintone-space-writer` | Productivity | `v0.1.0` | [`forestsheep911/kintone-space-writer`](https://github.com/forestsheep911/kintone-space-writer) -> `plugins/kintone-space-writer` |
| `kintone-setup-toolkit` | Productivity | `v0.1.0` | [`forestsheep911/kintone-setup-toolkit-codex-plugin`](https://github.com/forestsheep911/kintone-setup-toolkit-codex-plugin) -> `plugins/kintone-setup-toolkit` |

`deckit` is an image-first presentation plugin. It turns a topic, text, PDF, or
URL input into a deck workflow: source intake, deck brief, storyboard,
per-slide image prompts, generated full-slide images, review, standard preview
image, and final packaging.

Current Deckit delivery targets are non-editable image-container PPTX and
image-only PDF. The `.pptx` output is a packaging format around generated slide
PNGs, not a native editable PowerPoint deck. See the
[`forestsheep911/deckit`](https://github.com/forestsheep911/deckit) repository
for usage and contribution docs.

## Refresh after a plugin release

When a plugin in this marketplace publishes a new version:

1. In the plugin's own repository, push a matching tag, for example `vX.Y.Z`.
2. In this repository, bump that plugin's `source.ref` in
   `.agents/plugins/marketplace.json` to the same tag.
3. Update this README's plugin table so the documented pinned ref matches the
   marketplace catalog.
4. Commit and push. Users pick up the new version on their next
   `codex plugin marketplace upgrade`.

For Deckit specifically, verify both sides before announcing a release:

```bash
git ls-remote --tags https://github.com/forestsheep911/deckit.git refs/tags/vX.Y.Z
```

```bash
curl -fsSL https://raw.githubusercontent.com/forestsheep911/codex-plugin-marketplace-2water/main/.agents/plugins/marketplace.json
```

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

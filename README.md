# ui

A [shadcn](https://ui.shadcn.com)-compatible component registry — 100 React + Tailwind components and variants, installable straight into any project via the shadcn CLI.

Every component here is generated from and mirrors [shrutishankarnarayanan.com/components](https://www.shrutishankarnarayanan.com/components/), where you can preview each one live before installing it.

## Install

### 1. Register the namespace (one-time, per project)

```bash
npx shadcn@latest registry add @ui-shrushank=https://raw.githubusercontent.com/Shrootiiii/ui/main/r/{name}.json
```

This adds an entry to your project's `components.json` so the shadcn CLI knows how to resolve `@ui-shrushank/*` references. Run it once per project — not once per component.

### 2. Install a component

```bash
npx shadcn@latest add @ui-shrushank/primary-button
```

This drops the component's source directly into `components/ui/` in your project — no package to install, no version to pin, no runtime dependency on this repo. Any component that uses [Framer Motion](https://www.framer.com/motion/) declares it as a dependency, which the CLI installs automatically.

### 3. Install everything at once

```bash
npx shadcn@latest add @ui-shrushank/all
```

Works with `bunx --bun`, `pnpm dlx`, or `yarn dlx` in place of `npx` too.

## What's in here

| | |
|---|---|
| **Buttons & inputs** | `primary-button` `ghost-button` `toggle-switch` `text-field` `icon-button` `select` `checkbox` `slider` `intent-aware-button` `document-upload` `hover-border-gradient` `notification-button` `moving-border-button` |
| **Cards & layout** | `content-card` `stat-card` `badge` `pricing-card` `avatar` `avatar-group` `wave-card` `glow-card` `hover-reveal-card` `accordion` `testimonial-card` `pull-quote` `swipe-cards` `testimonial-carousel` `mini-chart` `link-preview-card` `intelligent-empty-state` |
| **Navigation** | `pill-tabs` `breadcrumbs` `command-palette` `pagination` `stepper` `icon-stepper` `comet-stepper` `dropdown-menu` `dock-nav` `rail-nav` `sidebar-nav` |
| **Motion & interaction** | `reveal-on-scroll` `logo-wall` `marquee` `parallax` `card-stack-scroll` `spotlight-card` `magnetic-button` `tooltip` `infinite-moving-cards` `text-generate-effect` |
| **Feedback & status** | `history-rail` `orbit-loader` `pulse-loader` `thinking-loader` `empty-state` `success-state` `error-state` `attention-gradient` `recovery-diff` `scope-preview` `consent-ledger` `cost-preview` `silent-failure-surface` `presence-indicator` `toast` `skeleton-loader` `undoable-action` `waiting-state` `permission-negotiator` |
| **AI interface** | `share-card` `share-sheet` `chat-input-bar` `chain-of-thought` `reasoning` `confirmation` `confidence-slider` `decision-timeline` `interruptible-automation` `sources` `suggestion` `tool` `artifact` `code-block` `commit` `file-tree` `sandbox` `test-results` `terminal` `audio-player` `audio-scrubber` `persona` `transcription` `voice-selector` `attachments` `settings-panel` `app-widget` |
| **Templates** | `ai-landing-template` `saas-landing-template` `premium-saas-homepage-template` |

Browse every one of these live, with a preview and copyable source, at [shrutishankarnarayanan.com/components](https://www.shrutishankarnarayanan.com/components/).

## Repo structure

```
registry.json     # Manifest listing every item in this registry
r/                # One JSON file per component (shadcn registry-item schema)
  primary-button.json
  ghost-button.json
  ...
  all.json        # Convenience item that installs every component at once
```

Each file under `r/` conforms to shadcn's [`registry-item.json`](https://ui.shadcn.com/docs/registry/registry-item-json) schema: a name, title, description, dependencies, and the component's source embedded as a `files` entry. `registry.json` conforms to the [`registry.json`](https://ui.shadcn.com/docs/registry/registry-json) schema and lists every item in one place.

## Where this content comes from

This repo isn't hand-maintained — it's generated output. The actual source of every component lives in the [portfolio site's repo](https://www.shrutishankarnarayanan.com), where each one is written once as a real, rendered React component and then built into the JSON files here via `next build`'s static export. When a component changes on the site, this repo gets re-synced from that build output and re-pushed; it doesn't get edited directly.

## License

MIT — use any of these components in your own projects, no attribution required.

# ui

A [shadcn](https://ui.shadcn.com)-compatible component registry: the free tier of a 181-component React + Tailwind library, installable straight into any project via the shadcn CLI.

The seven components here are free and MIT-licensed. The other 174 (blocks, charts, AI interface pieces and full templates) are in [ui-shrushank Pro](https://www.shrutishankarnarayanan.com/components/), a single purchase that unlocks a private registry with the same install flow.

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

| Component | What it is |
|---|---|
| `primary-button` | The default call to action, solid fill with hover and focus states. |
| `ghost-button` | A lower-emphasis outline button for secondary actions. |
| `badge` | A small status pill with neutral, success, and warning tones. |
| `text-field` | A labeled text input with clear focus and placeholder states. |
| `toggle-switch` | An accessible on/off switch built on a native button. |
| `breadcrumbs` | A simple breadcrumb trail with an aria-current page marker. |
| `commit-graph` | A contribution heatmap paged by two-week sprints, drillable to the day. |

`all` installs the seven in one go.

Browse these and the full library live, with a preview and (for free items) copyable source, at [shrutishankarnarayanan.com/components](https://www.shrutishankarnarayanan.com/components/).

## Repo structure

```
registry.json     # Manifest listing every item in this registry
r/                # One JSON file per component (shadcn registry-item schema)
  primary-button.json
  ghost-button.json
  ...
  all.json        # Convenience item that installs every free component at once
```

Each file under `r/` conforms to shadcn's [`registry-item.json`](https://ui.shadcn.com/docs/registry/registry-item-json) schema: a name, title, description, dependencies, and the component's source embedded as a `files` entry. `registry.json` conforms to the [`registry.json`](https://ui.shadcn.com/docs/registry/registry-json) schema and lists every item in one place.

## Where this content comes from

This repo isn't hand-maintained — it's generated output. The actual source of every component lives in the [portfolio site's repo](https://www.shrutishankarnarayanan.com), where each one is written once as a real, rendered React component and then built into the JSON files here via `next build`'s static export. A `sync-registry` job in that repo's deploy workflow pushes the fresh build output (`r/*.json` and `registry.json`) here automatically on every deploy to `main`; it doesn't get edited directly.

## License

MIT for everything in this repo: use these components in your own projects, no attribution required. Pro components are licensed separately under the [terms](https://www.shrutishankarnarayanan.com/legal/terms/) shown at purchase.

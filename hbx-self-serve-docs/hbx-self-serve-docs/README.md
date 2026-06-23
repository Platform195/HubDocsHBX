# HBX Self Serve Docs (Mintlify)

Documentation site for **HBX Self Serve** — the self-service advertising portal
that lets hotels promote themselves across the HBX Group B2B network. Built with
[Mintlify](https://mintlify.com/) and intended to publish under
`docs.app.uplifthub.io/HBX-self-serve/`.

## Local development

```bash
# 1. Install the Mintlify CLI (one time)
npm i -g mint

# 2. From this folder
mint dev
# → http://localhost:3000
```

`mint dev` watches MDX files and live-reloads.

## Folder layout

```
.
├── docs.json                # site config: nav, theme, branding
├── index.mdx                # home
├── favicon.svg              # placeholder — replace with HBX favicon
├── logo/
│   ├── light.svg            # placeholder — replace with HBX logo (light bg)
│   └── dark.svg             # placeholder — replace with HBX logo (dark bg)
├── snippets/                # reusable MDX bits (Ui, Pill)
├── get-started/
├── packages/
├── campaigns/               # the 5-step campaign wizard
├── checkout/
├── managing/                # Dashboard, Campaigns, Hotels, Purchases (stubs)
├── reference/               # glossary, support
└── images/                  # screenshots (add per page)
```

## Authoring

- All pages are **MDX** — Markdown plus components.
- Use Mintlify's built-in components for callouts and structure:

  ```mdx
  <Tip>Pro tip body</Tip>
  <Note>Useful aside</Note>
  <Warning>Heads-up</Warning>

  <Steps>
    <Step title="Open Packages">…</Step>
    <Step title="Click Create Campaign">…</Step>
  </Steps>
  ```

- Reference UI elements inline with the `<Ui>` snippet:
  ```mdx
  import { Ui } from "/snippets/ui.mdx";

  Click <Ui>Confirm selection</Ui> to continue.
  ```

See `EDITORIAL.md` for voice and formatting rules.

## Before you publish — placeholders to confirm

This scaffold uses sensible placeholders. Swap these for the real values:

| Item | Where | Notes |
| --- | --- | --- |
| Brand colours | `docs.json` → `colors` | Currently a teal matching the portal's primary buttons. Replace with official HBX hex codes. |
| Logo + favicon | `logo/*.svg`, `favicon.svg` | Text-based placeholders. Drop in the real HBX assets. |
| Portal URL | `docs.json` → `navbar.primary.href` | Points at `app.uplifthub.io/HBX-self-serve/`. Confirm the production portal URL. |
| Support contact | `docs.json` navbar link, `reference/support.mdx`, `index.mdx` | Uses `support@uplifthub.io`. Confirm the right contact for HBX advertisers. |
| Pricing figures | `packages/*`, `campaigns/*` | Taken from the screenshots and marked indicative. Confirm before publishing. |
| Screenshots | every page has `<Note>Screenshot coming soon.</Note>` | Add images under `images/` and replace the notes with `<Frame>` blocks. |

## Stubs to complete

The **Managing your account** section (`managing/`) contains placeholder pages
for **Dashboard**, **Campaigns**, **Hotels** and **Purchases** — screens not yet
captured. Fill these in once you have the UI walkthroughs.

## Adding screenshots

Save images under `images/<section>/<name>.png` (2× resolution preferred, trimmed
to the relevant UI area), then replace the placeholder note:

```mdx
<Frame caption="The package selector with Core selected.">
  <img src="/images/campaigns/select-package.png" alt="Select package step" />
</Frame>
```

## Deployment

1. Push this folder to a GitHub repo.
2. Connect the repo in your Mintlify dashboard (Settings → GitHub).
3. Mintlify auto-builds on every push to `main`. Point the custom domain/subpath
   at it via Settings → Custom Domain.

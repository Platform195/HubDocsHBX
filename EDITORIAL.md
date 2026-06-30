  # Editorial guide

A short reference for everyone writing HBX Self Serve docs. Stick to these and
the site stays consistent.

## Voice

- **Second person, active voice.** "Open the campaign, then click Confirm."
  Not "the campaign should be opened by the user".
- **Present tense.** "The summary shows…" — not "will show…".
- **British English.** "Customise", "organise", "behaviour".
- **Audience is the advertiser** — a hotel promoting itself. Assume no prior
  knowledge of the HBX/Uplift internals; explain in plain terms.

## Structure for any "how to" page

1. **One-line description** in frontmatter.
2. **Lead paragraph** — what this is and when you'd do it. No "Introduction" heading.
3. **Steps** in a `<Steps>` block.
4. **Optional `<Tip>` / `<Note>` / `<Warning>`** for caveats.
5. **Screenshot** in a `<Frame>` if it materially helps.

Avoid "Introduction", "Conclusion", "Overview" headings — the lead paragraph
covers them.

## Component cheat sheet

| Component                              | Use for                                  |
| -------------------------------------- | ---------------------------------------- |
| `<Tip>`                                | Helpful pro-tip — green                  |
| `<Note>`                               | Neutral aside — blue                     |
| `<Warning>`                            | Heads-up / known issue — yellow/red      |
| `<Steps>` + `<Step title="…">`         | Numbered procedure                       |
| `<CardGroup cols={2}>` + `<Card>`      | Landing / hub page link grid             |
| `<AccordionGroup>` + `<Accordion>`     | FAQ, glossary, anything browsable        |
| `<Frame caption="…">`                  | Screenshot wrapper                       |
| `<Ui>Confirm</Ui>` (snippet)           | Inline UI reference (button name etc.)   |

## Naming UI elements

- **Bold** for screen names: "Open the **Packages** screen."
- **`<Ui>`** for clickable elements: "Click <Ui>Create Campaign</Ui>."
- Backticks for field values: "Set the market to `UK & Ireland`."

## Linking

- Internal links use absolute paths without `.mdx`: `/campaigns/select-package`.
- External links use full URLs.

## Pricing and figures

- Prices come from the product, not memory. Mark them indicative and confirm
  before publishing; pricing can change.

## Screenshots

- Save under `images/<section>/` at the project root.
- 2× resolution preferred; trim to the relevant area.
- Use `<Frame caption="…">` to caption. Until an image exists, leave a
  `<Note>Screenshot coming soon.</Note>` placeholder.

## When in doubt

Match the tone of the **Creating a campaign** wizard pages — they're the
canonical example for this site.

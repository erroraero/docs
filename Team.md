# Docs Editing Team

The people responsible for maintaining and improving the [nxtdev.xyz](https://nxtdev.xyz) documentation.

---

## Team Members

| Name | GitHub |
|---|---|
| Ebnnxyz | [@Ebnnxyz](https://github.com/Ebnnxyz) |
| Mishal | [@Mishal](https://github.com/Mishal) |
| Bhrxth | [@Bhrxth](https://github.com/Bhrxth) |

---

## Onboarding Guide

Welcome to the nxtdev docs team. Here's everything you need to get up and running.

### 1. Get Access

Make sure you have:
- [ ] Been added as a collaborator on this repo
- [ ] Write access confirmed — try cloning the repo locally
- [ ] Reviewed the `CODEOWNERS` file so you know who owns what

### 2. Set Up Local Preview

Install the Mintlify CLI:

```bash
npm i -g mint
```

Clone the repo and start the local dev server:

```bash
git clone https://github.com/nxtdev-xyz/docs.git
cd docs
mint dev
```

Preview runs at `http://localhost:3000`. If it looks broken, run `mint update` first.

### 3. Understand the Workflow

Direct pushes to `main` are blocked. All changes go through a PR:

```
create branch → make changes → open PR → get 1 approval → merge
```

- Branch naming: `docs/topic-name` or `fix/what-you-fixed`
- Always fill out the PR template
- Tag a teammate for review — don't leave PRs sitting

### 4. Mintlify Basics

The docs are written in **MDX** (Markdown + JSX). Key things to know:

- **`docs.json`** — controls navigation, sidebar, and site config
- **`/pages`** — where all the content files live  
- Mintlify components like `<Card>`, `<Tabs>`, `<CodeGroup>` are available out of the box
- Check the [Mintlify component reference](https://mintlify.com/docs/components) when building new pages

### 5. Writing Standards

- Use clear, concise language — docs are for developers, skip the fluff
- Headings should be sentence case: `Getting started` not `Getting Started`
- Code blocks must always have a language tag (` ```bash `, ` ```json `, etc.)
- Test all links before opening a PR
- If you're adding a new page, register it in `docs.json` navigation or it won't show up

### 6. AI-assisted Writing

Speed things up with the Mintlify skill for your AI tool:

```bash
npx skills add https://mintlify.com/docs
```

Works with Claude Code, Cursor, Windsurf, and others.

---

## Mintlify Tips, Tricks & Styling

### Components Cheatsheet

The most useful MDX components and when to use them:

**Callouts** — 5 types, use the right one:
```mdx
<Note>Supplementary info the reader should know</Note>
<Tip>A shortcut or best practice</Tip>
<Info>Neutral contextual information</Info>
<Warning>Something that could break or go wrong</Warning>
<Check>Confirmation or success state</Check>
```

**Cards & CardGroup** — great for landing/overview pages:
```mdx
<CardGroup cols={2}>
  <Card title="Getting Started" icon="rocket" href="/quickstart">
    Set up your subdomain in minutes.
  </Card>
  <Card title="API Reference" icon="code" href="/api">
    Full API docs with playground.
  </Card>
</CardGroup>
```

**Accordion** — hide wall-of-text content behind a toggle:
```mdx
<AccordionGroup>
  <Accordion title="What is nxtdev.xyz?">
    A free subdomain registry for developers.
  </Accordion>
  <Accordion title="Is it really free?">
    Yes, completely free for open source and personal projects.
  </Accordion>
</AccordionGroup>
```

**Tabs** — show the same thing multiple ways (OS, language, etc.):
```mdx
<Tabs>
  <Tab title="npm">
    ```bash
    npm install nxtdev-cli
    ```
  </Tab>
  <Tab title="pnpm">
    ```bash
    pnpm add nxtdev-cli
    ```
  </Tab>
</Tabs>
```

**Steps** — always use this for sequential instructions, never a numbered list:
```mdx
<Steps>
  <Step title="Register">
    Go to nxtdev.xyz and pick your subdomain.
  </Step>
  <Step title="Configure DNS">
    Add the CNAME record to your DNS provider.
  </Step>
  <Step title="Done">
    Your subdomain is live within minutes.
  </Step>
</Steps>
```

**Code block with filename + line highlight:**
````mdx
```bash nginx.conf {3}
server {
  listen 80;
  server_name yourname.nxtdev.xyz; # this line is highlighted
}
```
````

---

### Page Frontmatter Tricks

Every `.mdx` file supports frontmatter at the top. Useful fields:

```mdx
---
title: "Getting Started"
description: "Set up your nxtdev subdomain in under 5 minutes"
icon: "rocket"
mode: "wide"
---
```

- `mode: "wide"` — removes right-side ToC, full width content
- `mode: "custom"` — minimal layout, no sidebar or ToC (great for landing pages)
- `mode: "center"` — centered content, good for changelogs
- `icon` — any Font Awesome icon name, shows in the sidebar next to the page title

---

### docs.json Styling

Brand colors and theme live in `docs.json`:

```json
{
  "colors": {
    "primary": "#6366f1",
    "light": "#818cf8",
    "dark": "#4f46e5"
  },
  "theme": "maple"
}
```

**Available themes:** `mint`, `maple`, `palm`, `linden`, `willow`, `sage`, `oak`, `chestnut`, `kernel`, `almond`
- `maple` — modern/clean, good for SaaS and dev tools
- `willow` — minimal and distraction-free
- `oak` — structured, best for large doc sets

---

### Custom CSS

Add a `.css` file to the repo, reference it in `docs.json` under `custom_css`, and target Mintlify's selectors directly:

```css
/* Style the active sidebar item */
nav-item[data-active] {
  font-weight: 600;
}

/* Target callout component */
callout {
  border-radius: 8px;
}
```

Use Tailwind classes like `dark:hidden` / `dark:block` on HTML elements for dark mode control.
Avoid inline `style=` props — they can cause layout shift on load.

---

### Web Editor Shortcuts

When editing in the Mintlify web editor at `dashboard.mintlify.com`:

| Action | Shortcut |
|---|---|
| Open AI agent | `Cmd/Ctrl + I` |
| Inline AI on empty line | `Space` |
| Insert a component | `/` |
| Switch visual ↔ markdown mode | Toggle in toolbar |

Markdown mode uses Monaco (same engine as VS Code) — all VS Code keyboard shortcuts work.

---

### Branch Previews

Every branch you push gets an automatic live preview URL:

```
https://<org>-<branch-name>.mintlify.app
```

Share this in your PR so reviewers can see the rendered output — not just raw MDX.

---

### LLM Indexing

Mintlify auto-generates `/llms.txt` for your docs — used by AI tools like Cursor, Windsurf, and Claude Code to index your content. No config needed, on by default.

To pull your docs inline in Cursor or Windsurf:
```
@docs:https://docs.nxtdev.xyz
```

---

## Questions?

Open a [GitHub Discussion](https://github.com/nxtdev-xyz/docs/discussions) or ping a teammate directly.

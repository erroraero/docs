# nxtdev.xyz — Docs

Official documentation for [nxtdev.xyz](https://nxtdev.xyz) — a free subdomain registry for developers.

Built with [Mintlify](https://mintlify.com) and auto-deployed on every push to `main`.

---

## Contributing

We welcome contributions from the community — typo fixes, content improvements, new guides, whatever helps developers get started faster.

### Before you start

- All changes go through a **Pull Request** — direct pushes to `main` are blocked
- PRs require **1 approval** from a maintainer before merging
- Use the issue and PR templates provided

### Making a change

1. Fork the repo
2. Create a branch — `docs/your-change` or `fix/broken-link`
3. Make your changes
4. Open a PR and fill out the template
5. Wait for review ✅

---

## Local Development

Install the Mintlify CLI:

```bash
npm i -g mint
```

Run the local preview at the root of the repo (where `docs.json` lives):

```bash
mint dev
```

Preview available at `http://localhost:3000`.

> If something looks off, run `mint update` to grab the latest CLI version.

---

## AI-assisted Writing

Set up your AI coding tool to work with Mintlify:

```bash
npx skills add https://mintlify.com/docs
```

Works with Claude Code, Cursor, Windsurf, and others. See the [AI tools guide](https://mintlify.com/docs/ai-tools) for tool-specific setup.

---

## Deployment

This repo is connected to Mintlify via the GitHub app. Every merge to `main` triggers an automatic production deployment — no manual steps needed.

---

## Maintainers

| GitHub | Role |
|---|---|
| [@erroraero](https://github.com/erroraero) | Maintainer |
| [@aviorxt](https://github.com/aviorxt) | Maintainer |
| [@avrxtcloud](https://github.com/avrxtcloud) | Maintainer |

---

## Resources

- [nxtdev.xyz](https://nxtdev.xyz)
- [Mintlify Docs](https://mintlify.com/docs)
- [Open an Issue](https://github.com/nxtdev-xyz/docs/issues/new/choose)

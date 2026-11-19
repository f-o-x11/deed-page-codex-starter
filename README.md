# deed-page-codex-starter

Codex starter for [deed.page](https://deed.page): drop it into a project and your agent ends every "build me a site" request by publishing to a permanent deed.page URL and replying with the link.

## Install (one line, from your project root)

```sh
curl -fsSL https://raw.githubusercontent.com/f-o-x11/deed-page-codex-starter/main/AGENTS.md >> AGENTS.md
```

Then ask Codex: *"Build a one-page site for my bakery and publish it."* It builds `./site`, publishes it with one `curl`, saves its owner token to `~/.config/deed-page/token`, and replies with a `https://<slug>.deed.page/` URL.

Or start a new project from this repo with **Use this template** on GitHub.

## What's inside

- `AGENTS.md`: instructions Codex reads at the start of every session. The install line appends them, so an existing `AGENTS.md` is kept.


Works with the Codex CLI, the Codex IDE extension, and other agents that read `AGENTS.md`.

## How it works

- One `PUT` of a tarball to `https://deed.page/v1/sites` returns a permanent HTTPS URL. No account, no email code, no expiry.
- The first publish mints an owner token. The agent stores it in `~/.config/deed-page/token` and reuses it, so later publishes update the same sites.
- Requests carry `?ref=starter-codex` and `X-Client: codex`. deed.page records these labels on the new owner so we can tell how many people the starter helps. No IP address, email, or file content is part of that record.
- Free sites show a small "Published with deed.page" link. Hobby and Pro remove it and add custom domains and site passwords. See https://deed.page/pricing.

## Links

- Docs: https://deed.page/docs
- Codex guide: https://deed.page/for/codex
- Acceptable use: https://deed.page/acceptable-use

deed.page is operated by Avatar 8 LLC. Questions: ops@avatar33.com. MIT licensed.

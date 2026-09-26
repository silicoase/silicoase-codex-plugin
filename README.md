# Silicoase Codex plugin

This repository hosts the Silicoase Codex plugin marketplace. The current branch is a technical candidate for [SIL-65](https://linear.app/silicoase/issue/SIL-65).

The plugin points to the public Alpha MCP endpoint. It contains no credentials or customer data. Its package and MCP registration load in Codex CLI 0.155.1 using an isolated local marketplace. OAuth sign-in, Codex desktop behavior, Windows behavior, and the customer journey still require isolated verification. The marketplace uses `ON_USE` until automatic OAuth registration is validated under [SIL-56](https://linear.app/silicoase/issue/SIL-56). Do not present this candidate as a working customer setup path yet.

Release plan: validate the pinned Git marketplace on Codex desktop and CLI, prove Clerk authorization and the compact account/request/bid/approval journey with an admitted test user, then tag the tested commit and update the website and client setup guide.

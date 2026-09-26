# Silicoase Codex plugin

This repository hosts the Silicoase Codex plugin marketplace for [SIL-65](https://linear.app/silicoase/issue/SIL-65). The package currently describes version 0.1.1 and points to the public Alpha MCP endpoint. It contains no credentials or customer data. The marketplace uses `ON_USE` until automatic OAuth registration is validated under [SIL-56](https://linear.app/silicoase/issue/SIL-56).

## Verification status

A fresh, disposable `CODEX_HOME` with Codex CLI 0.155.1 added the public Git marketplace from `main`, installed `silicoase@silicoase`, and listed its remote HTTP MCP server at `https://alpha.silicoase.com/mcp`. The MCP auth status was `o_auth`; no OAuth sign-in or admitted account read was performed. This establishes CLI package installation only.

On macOS, the locally inspected ChatGPT desktop app is 26.917.71314 (build 10954), with bundled Codex CLI 0.155.0-alpha.16.4. Native app marketplace discovery, plugin installation, MCP registration, prompt-based setup, and sign-in remain untested. [OpenAI's plugin packaging docs](https://developers.openai.com/plugins/build/plugins) say a newly added local or repository marketplace appears in the desktop Plugins Directory after restarting the app. A single onboarding prompt therefore cannot be claimed to complete the app flow without a tested restart and follow-up.

Windows desktop behavior has not been tested for Silicoase. [OpenAI Codex issue #26693](https://github.com/openai/codex/issues/26693) is an open report of a plugin's HTTP MCP server failing to register in the Windows desktop app (reporter version 26.602.40724). It is a compatibility risk, not proof that this version of Silicoase fails on current Windows builds. No Windows fallback has been verified.

Do not present this candidate as a working customer setup path yet. Next, test native desktop install and prompt handling in an isolated profile, complete the Clerk authorization and compact account/request/bid/approval journey with an admitted test user, test Windows or establish a verified fallback, then tag the tested commit and update the website and client setup guide.

# Silicoase Codex plugin

This repository hosts the Silicoase Codex plugin marketplace for [SIL-65](https://linear.app/silicoase/issue/SIL-65). The package currently describes version 0.1.1 and points to the public Alpha MCP endpoint. It contains no credentials or customer data. The marketplace uses `ON_USE` until automatic OAuth registration is validated under [SIL-56](https://linear.app/silicoase/issue/SIL-56).

## Verification status

A fresh, disposable `CODEX_HOME` with Codex CLI 0.155.1 added the public Git marketplace from `main`, installed `silicoase@silicoase`, and listed its remote HTTP MCP server at `https://alpha.silicoase.com/mcp`. A repeat on September 26 also refreshed the Git marketplace and reinstalled the plugin successfully. The first profile reported MCP auth status `o_auth`; the repeat profile reported `unknown`. Neither completed OAuth sign-in or an admitted account read. This establishes CLI package installation and refresh only.

## CLI installation rehearsal

These commands were checked with Codex CLI 0.155.1 in a disposable profile. They install the package, not an authenticated Silicoase connection:

```sh
codex plugin marketplace add silicoase/silicoase-codex-plugin --ref main
codex plugin add silicoase@silicoase
codex plugin list
codex mcp list
```

The expected MCP entry is named `silicoase` with transport `streamable_http` and URL `https://alpha.silicoase.com/mcp`. To pull a later Git marketplace revision, refresh the marketplace and reinstall the plugin, then start a new Codex task before checking its tools:

```sh
codex plugin marketplace upgrade silicoase
codex plugin add silicoase@silicoase
```

The marketplace currently follows `main`; it is not a tagged customer release. Check the installed version and source with `codex plugin list` before attributing any behavior to this package. Do not infer desktop installation or OAuth success from these CLI commands.

On macOS, the locally inspected ChatGPT desktop app is 26.917.71314 (build 10954), with bundled Codex CLI 0.155.0-alpha.16.4. Native app marketplace discovery, plugin installation, MCP registration, prompt-based setup, and sign-in remain untested. [OpenAI's plugin packaging docs](https://developers.openai.com/plugins/build/plugins) say a newly added local or repository marketplace appears in the desktop Plugins Directory after restarting the app. A single onboarding prompt therefore cannot be claimed to complete the app flow without a tested restart and follow-up. The next desktop qualification should observe the marketplace in Plugins Directory, install `silicoase`, start a new task, inspect the actual MCP connection, and only then attempt an isolated admitted-user OAuth journey.

Windows desktop behavior has not been tested for Silicoase. [OpenAI Codex issue #26693](https://github.com/openai/codex/issues/26693) is an open report of a plugin's HTTP MCP server failing to register in the Windows desktop app (reporter version 26.602.40724). It is a compatibility risk, not proof that this version of Silicoase fails on current Windows builds. No Windows fallback has been verified.

Do not present this candidate as a working customer setup path yet. Next, test native desktop install and prompt handling in an isolated profile, complete the Clerk authorization and compact account/request/bid/approval journey with an admitted test user, test Windows or establish a verified fallback, then tag the tested commit and update the website and client setup guide.

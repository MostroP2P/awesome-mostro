<h1 align="center">Awesome Mostro <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome"></a></h1>

<p align="center">
  <img src="assets/logo.png" alt="Mostro" width="360">
</p>

<p align="center"><b>English</b> · <a href="README.es.md">Español</a></p>

A curated, collaborative list of awesome resources, clients, tools and projects for [Mostro](https://mostro.network), the peer-to-peer Bitcoin exchange on Lightning Network and Nostr.

## What's Mostro?

Mostro is a non-custodial, peer-to-peer platform for buying and selling Bitcoin over the Lightning Network, using [Nostr](https://nostr.com) as its communication layer. There are no accounts and no KYC, and nobody ever holds the traders' funds: the seller's sats are locked with a hold invoice until the trade is complete.

Anyone can run their own Mostro node (`mostrod`) and serve their community. Visit [mostro.network](https://mostro.network) to learn more.

## Contents

- [The Mostro protocol](#the-mostro-protocol)
- [Daemon](#daemon)
- [Clients](#clients)
- [Libraries](#libraries)
- [Disputes and administration](#disputes-and-administration)
- [Node operation](#node-operation)
- [Statistics and monitoring](#statistics-and-monitoring)
- [AI and agents](#ai-and-agents)
- [Developer tools and testing](#developer-tools-and-testing)
- [Documentation](#documentation)
- [Websites and community](#websites-and-community)
- [Archived](#archived)
- [Contributing](#contributing)

## The Mostro protocol

Mostro is an open protocol: orders, trades, disputes and ratings are Nostr events that any client can read and build on.

- [Protocol specification](https://mostro.network/protocol/) ([source](https://github.com/MostroP2P/protocol)) is the documentation site for the Mostro specifications.
- [NIP-69](https://github.com/nostr-protocol/nips/blob/master/69.md) is the Nostr standard for peer-to-peer order events (kind 38383) that Mostro uses to publish its orders, so that different P2P platforms can share one liquidity pool.

## Daemon

- [mostro](https://github.com/MostroP2P/mostro) is `mostrod`, the Mostro daemon in Rust that matches orders, manages hold invoices and talks to clients over Nostr.
- [mostro-startos](https://github.com/MostroP2P/mostro-startos) is the StartOS package to run a Mostro node on StartOS.

## Clients

- [Mostro App](https://github.com/MostroP2P/app) is the official client for Android, Windows, macOS, Linux, iOS and the [web](https://mostro.network/app/), with a Rust core and a Flutter UI.
- [mostro-cli](https://github.com/MostroP2P/mostro-cli) is the command-line client, with a versioned JSON interface (`--output json`) for driving it from programs.
- [Mostrix](https://github.com/MostroP2P/mostrix) is a terminal (TUI) client for Mostro, with an admin mode for dispute solvers.

## Libraries

- [mostro-core](https://github.com/MostroP2P/mostro-core) is the Rust crate with the common types shared by Mostro and its clients.
- [dart-nip44](https://github.com/MostroP2P/dart-nip44) is a Dart implementation of NIP-44 encryption (fork).

## Disputes and administration

- [Bosstro](https://github.com/MostroP2P/bosstro) is the Android app for dispute solvers: take disputes, chat with both parties, and pay the buyer or refund the seller from a phone.
- [Serbero](https://github.com/MostroP2P/serbero) is a dispute assistant that makes sure every dispute reaches the solvers, talks to both parties and hands the case to a solver with a clear summary when needed.
- [Serbero (legacy)](https://github.com/MostroP2P/serbero_legacy) is the earlier dispute coordination and notification system.
- [mostro-watchdog](https://github.com/MostroP2P/mostro-watchdog) is a notification bot for Mostro administrators that monitors dispute events and sends real-time Telegram alerts.

## Node operation

- [Mostromancer](https://github.com/MostroP2P/mostromancer) is a web wizard that configures a Mostro node and generates a Docker installer for it, optionally with LND, Bitcoin Core and Lightning Terminal. It runs entirely in the browser.
- [mostro-push-server](https://github.com/MostroP2P/mostro-push-server) is the push notification server for the Mostro mobile app.
- [scripts-mostro](https://github.com/21Mill/scripts-mostro) is a set of management, monitoring and automation scripts for a Mostro node: verified updates and rollbacks, read-only database snapshots, accounting, and Telegram and Nostr bots that publish offers (in Spanish).

## Statistics and monitoring

- [Semáforo](https://status.mostro.network) ([source](https://github.com/MostroP2P/semaforo)) is the public status page of trusted Mostro instances, built from signed health events (kind 38389) verified in the browser.
- [Bestiario](https://github.com/MostroP2P/bestiario) computes statistics for the Mostro network from the public Nostr events its instances publish; [bestiario-fe](https://github.com/MostroP2P/bestiario-fe) is its frontend, which verifies the signed events in the browser.
- [mostro-score](https://github.com/MostroP2P/mostro-score) is a CLI tool that calculates reputation statistics for Mostro nodes from public Nostr events; [mostro-score-web](https://github.com/MostroP2P/mostro-score-web) is its web version.
- [mstats](https://github.com/MostroP2P/mstats) is a trading statistics CLI that joins development fee events (kind 8383) with order events (kind 38383) to report global and per-node figures.
- [tasaK](https://github.com/Forte11Cuba/tasak) calculates the exchange rate of a local currency from completed orders on one or more Mostro nodes, with every order verifiable on Nostr. The example configuration is Kmbalache (CUP 🇨🇺).

## AI and agents

- [mostro-mcp](https://github.com/MostroP2P/mcp) is an [MCP](https://modelcontextprotocol.io) server that lets AI agents trade on Mostro by driving `mostro-cli`.
- [mostro-skill](https://github.com/MostroP2P/mostro-skill) is an AI skill for trading on Mostro that lets agents interact with it over Nostr.
- [mostro-cli-book](https://github.com/MostroP2P/mostro-cli-book) explains how to drive `mostro-cli` from a program: the JSON interface, every field, error and example.

## Developer tools and testing

- [mostro-regtest](https://github.com/MostroP2P/mostro-regtest) is a Docker regtest environment with Mostro, a Nostr relay, bitcoind, LND and ThunderHub.
- [mostro-webtool](https://github.com/MostroP2P/mostro-webtool) is a web tool for generating deterministic keys and building Mostro protocol messages.
- [mortsom](https://github.com/MostroP2P/mortsom) is an end-to-end test harness for the Mostro mobile application.
- [mostro-chat](https://github.com/MostroP2P/mostro-chat) is a minimalist peer-to-peer chat in Rust over Nostr.

## Documentation

- [docs-english](https://github.com/MostroP2P/docs-english) is the English user documentation site.
- [docs-spanish](https://github.com/MostroP2P/docs-spanish) is the Spanish user documentation site.

## Websites and community

- [mostro.network](https://mostro.network) ([source](https://github.com/MostroP2P/MostroP2P.github.io)) is the official website of Mostro.
- [Mostro blog](https://github.com/MostroP2P/blog) is the Mostro blog.
- [Mostro community](https://github.com/MostroP2P/community) is the Mostro community landing page.
- [Mostro Foundation](https://github.com/MostroP2P/mostro-foundation-website) is the website of the Mostro Foundation.
- [Mostro Store](https://store.mostro.network) ([source](https://github.com/MostroP2P/store)) is the Mostro T-shirt store, paid over Lightning with orders sent encrypted over Nostr (NIP-17).

## Archived

Projects that are no longer maintained, kept here for reference.

- [mobile](https://github.com/MostroP2P/mobile) was the first Flutter mobile client, superseded by the [Mostro App](https://github.com/MostroP2P/app).
- [documentation](https://github.com/MostroP2P/documentation) was the original Mostro documentation.
- [mostro.network](https://github.com/MostroP2P/mostro.network) is a deprecated website repository, superseded by [MostroP2P.github.io](https://github.com/MostroP2P/MostroP2P.github.io).
- [old-blog](https://github.com/MostroP2P/old-blog) was the old Zola blog.

## Contributing

Contributions are welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related rights to this work.

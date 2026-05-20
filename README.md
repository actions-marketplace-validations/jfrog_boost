<p align="center">
  <a href="https://jfrog.github.io/boost/">
    <picture>
      <source srcset=".github/assets/boost-logo-dark.png" media="(prefers-color-scheme: dark)">
      <source srcset=".github/assets/boost-logo-light.png" media="(prefers-color-scheme: light)">
      <img src=".github/assets/boost-logo-light.png" alt="Boost" width="260">
    </picture>
  </a>
</p>

<p align="center">
  <strong>Boost</strong> — faster agents, faster CI
</p>

<p align="center">
  <sub>For coding agents, their commands, and the CI that runs them.</sub>
</p>

<p align="center">
  <a href="https://jfrog.github.io/boost/"><img src="https://img.shields.io/badge/website-jfrog.github.io%2Fboost-36a13b?logo=googlechrome&logoColor=white" alt="Website"></a>
  <a href="https://github.com/jfrog/boost/releases"><img src="https://img.shields.io/github/v/release/jfrog/boost?color=36a13b" alt="Release"></a>
  <a href="https://go.dev/"><img src="https://img.shields.io/badge/go-1.25-00ADD8?logo=go&logoColor=white" alt="Go 1.25"></a>
  <img src="https://img.shields.io/badge/platform-linux%20%7C%20macOS%20%7C%20windows-lightgrey" alt="Platforms">
  <a href="https://github.com/jfrog/boost/releases"><img src="https://img.shields.io/github/downloads/jfrog/boost/total?color=6f42c1" alt="Downloads"></a>
  <a href="https://github.com/jfrog/boost/stargazers"><img src="https://img.shields.io/github/stars/jfrog/boost?style=flat&color=yellow" alt="Stars"></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/agent--native-brightgreen" alt="Agent-native">
  <img src="https://img.shields.io/badge/OpenTelemetry-enabled-blueviolet?logo=opentelemetry&logoColor=white" alt="OpenTelemetry">
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-proprietary%20(beta)-blue" alt="License: proprietary (beta)"></a>
</p>

<p align="center">
  <sub>Sponsored by <a href="https://jfrog.com"><strong>JFrog</strong></a></sub>
</p>

---

**Boost** turns noisy command runs into short, useful signals for agents and CI. It saves tokens, speeds up reruns, and helps teams build an agentic coding factory with one binary:

- your **terminal** — prefix any command with `boost`
- your **coding agent** — `boost init` wires up Cursor, Claude Code, Codex, Gemini CLI, and more
- your **CI** — one line: `uses: jfrog/boost@v0`

Same acceleration, same token savings, same CI visibility — wherever your builds run.

## Quick Start

**CLI** — prefix any command with `boost`

Install:

```bash
curl -fsSL https://raw.githubusercontent.com/jfrog/boost/main/install.sh | bash
```

Use:

```bash
boost docker build -t myapp .
boost npm ci
boost pytest
```

**Coding agent** — auto-wire Cursor, Claude Code, Codex, and more

Run the interactive setup in any project:

```bash
boost init
```

It detects your installed editors and CI providers and registers hooks so agent commands run through boost. Re-run it any time your editor / agent list changes.

**CI** — one line in your workflow

```yaml
steps:
  - uses: jfrog/boost@v0
  - uses: actions/checkout@v4
  ...
```

The action pins to the rolling `v0` major; see [releases](https://github.com/jfrog/boost/releases) for the latest tag.

## Why Boost

- **One binary for agents and CI** — local commands, coding agents, and workflows share the same fast path.
- **60–90% fewer log tokens** — noisy output becomes short summaries before it reaches your agent.
- **CI context agents can use** — wrapped commands expose timing, cache hits, and exit codes through OpenTelemetry.

## Before / after

Same `npm ci`, same result. What changes:

- **~15× fewer tokens** in your agent's context — 9.8k → 640 on a typical install.
- **Faster reruns** via content-addressed cache — seconds instead of minutes.
- **Clear CI signal** for every command — timing, cache hits, and exit code without the log wall.

```bash
# Without boost — ~9,800 tokens of log noise in your agent's context
$ npm ci
npm warn deprecated inflight@1.0.6 / rimraf@3.0.2 / glob@7.2.3 …
added 1285 packages, audited 1286 in 45s
found 0 vulnerabilities

# With boost — ~640 tokens, same result, cache-backed
$ boost npm ci
[OK] npm ci · 1,285 packages restored from boost cache in 2.4s · 0 vulnerabilities
```

## Supported tools

**Coding agents:** Cursor · Claude Code · GitHub Copilot · Codex CLI · Gemini CLI · OpenCode · Windsurf · Cline

**CI platforms:** GitHub Actions · GitLab CI *(coming soon)* · Jenkins *(coming soon)* · CircleCI *(coming soon)* · Azure Pipelines *(coming soon)*

## Usage examples

Prefix any command with `boost` — anywhere you'd normally run it.

- `boost docker build ...` — compressed build log and layer-cache summary
- `boost npm ci` — dependency summary, local package cache, retry-safe output
- `boost pytest` — quiet output on green runs, useful failures when tests break
- `boost gh run view --log` — CI logs condensed to top failures plus summary

## Update

```bash
boost update
```

## Documentation

See the [full documentation](https://jfrog.github.io/boost) for commands, configuration, OpenTelemetry export, and CI recipes.

## Security & Privacy

- **Local-first.** Command history and raw logs stay on your machine.
- **Only metadata leaves.** When Boost sends usage data, it goes only to JFrog to help improve the product. Exported metadata includes timing, exit code, and cache stats — never raw logs, file contents, or env values. Secrets matching patterns like `*_TOKEN`, `*_SECRET`, `AWS_*`, `DATABASE_URL` are redacted before write or export.
- **Open protocol, signed binaries.** OpenTelemetry-native. Binaries ship signed via GitHub Releases.

Full policy, supported versions, and how to report a vulnerability: see [SECURITY.md](./SECURITY.md).

## License

Copyright © 2026 JFrog Ltd. All rights reserved. See [LICENSE](LICENSE) and [BETA_AGREEMENT.md](BETA_AGREEMENT.md).

---

*Dedicated to the memory of Dima Gershovich — a brilliant engineer, a talented musician, and a dear friend.* [Read Dima's story](docs/memorial/MEMORIAL.md)
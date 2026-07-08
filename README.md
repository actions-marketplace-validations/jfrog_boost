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
  <strong>Save tokens. Maximize context.</strong>
</p>

<p align="center">
  <sub>Smart token savings for coding agents and shell commands.</sub>
</p>

<p align="center">
  <a href="https://jfrog.github.io/boost/"><img src="https://img.shields.io/badge/website-jfrog.github.io%2Fboost-36a13b?logo=googlechrome&logoColor=white" alt="Website"></a>
  <a href="https://github.com/jfrog/boost/releases"><img src="https://img.shields.io/badge/release-v0.7.5-36a13b" alt="Release"></a>
  <a href="https://go.dev/"><img src="https://img.shields.io/badge/go-1.25-00ADD8?logo=go&logoColor=white" alt="Go 1.25"></a>
  <img src="https://img.shields.io/badge/platform-linux%20%7C%20macOS%20%7C%20windows-lightgrey" alt="Platforms">
  <a href="https://github.com/jfrog/boost/releases"><img src="https://img.shields.io/badge/downloads-94k%2B-6f42c1" alt="Downloads: 94k+"></a>
  <a href="https://github.com/jfrog/boost/stargazers"><img src="https://img.shields.io/badge/stars-234-yellow" alt="Stars: 234"></a><br>
  <img src="https://img.shields.io/badge/agent--native-brightgreen" alt="Agent-native">
  <img src="https://img.shields.io/badge/OpenTelemetry-enabled-blueviolet?logo=opentelemetry&logoColor=white" alt="OpenTelemetry">
</p>

<p align="center">
  <sub>Sponsored by <a href="https://jfrog.com"><strong>JFrog</strong></a></sub>
</p>

---

<p align="center">
  <strong>Frogi, our mascot, appears when you run just <code>boost</code>.</strong>
</p>

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-mascot-dark.png" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-mascot-light.png" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-mascot-light.png" alt="Frogi, the Boost mascot" width="180">
  </picture>
</p>

**Boost** wraps the commands your agents already run, turning noisy logs into compact, structured context that keeps the signal — errors, timings, changed counts, cache hits — while cutting the noise.

Boost never trades quality for savings. It trims only what's safe to drop, so agent output stays just as sharp. Our [Terminal-Bench 2.0 benchmark](https://boost.jfrog.com/blog/benchmarks-terminal-bench/) shows it: identical task pass rate, ~12% lower cost — Boost keeps agents optimized without ever breaking their stride.

## Quick start

**Install Boost:**

```bash
curl -fsSL https://raw.githubusercontent.com/jfrog/boost/main/install.sh | bash
```

**Wire it into Cursor, Claude Code, Codex, Gemini CLI, and OpenCode:**

```bash
boost init
```

## Smart token savings

Boost does not just truncate output. It applies command-aware filters that preserve what agents need to reason about the result.

```bash
# Without Boost: ~9,800 tokens of install noise
$ npm ci
npm warn deprecated inflight@1.0.6 / rimraf@3.0.2 / glob@7.2.3 …
added 1285 packages, audited 1286 in 45s
found 0 vulnerabilities

# With Boost: ~640 tokens, same outcome, cache-backed
$ boost npm ci
[OK] npm ci · 1,285 packages restored from boost cache in 2.4s · 0 vulnerabilities
```

The agent sees the useful summary, not the scrollback. On failures, Boost keeps the failing test, compiler error, or stack frame that matters.

## See your savings

After wrapping commands, check how many tokens Boost kept out of your context window:

```bash
boost report
```

Open an interactive breakdown in your browser:

```bash
boost report -w
```

## What it wraps

- **Agents:** Cursor, Claude Code, GitHub Copilot, Codex CLI, Gemini CLI, OpenCode, Windsurf, Cline.
- **Commands:** Docker, npm, pytest, Git, GitHub CLI, and other shell commands pass through the same wrapper.

## Usage examples

- `boost docker build ...` — compressed build log and layer-cache summary
- `boost npm ci` — dependency summary, local package cache, retry-safe output
- `boost pytest` — quiet output on green runs, useful failures when tests break

## Update

```bash
boost update
```

## Documentation

See the [full documentation](https://jfrog.github.io/boost) for commands, configuration, and OpenTelemetry export.

## Security & Privacy

- **Local-first.** Command history and raw logs stay on your machine.
- **Only metadata leaves.** When Boost sends usage data, it goes only to JFrog to help improve the product. Exported metadata includes timing, exit code, and cache stats, never raw logs, file contents, or env values. Secrets matching patterns like `*_TOKEN`, `*_SECRET`, `AWS_*`, `DATABASE_URL` are redacted before write or export.
- **Open protocol, signed binaries.** OpenTelemetry-native. Binaries ship signed via GitHub Releases.

Full policy, supported versions, and how to report a vulnerability: see [SECURITY.md](./SECURITY.md).

## License

Copyright © 2026 JFrog Ltd. All rights reserved. See [LICENSE](LICENSE) and [BETA_AGREEMENT.md](BETA_AGREEMENT.md).

---

*Dedicated to the memory of Dima Gershovich — a brilliant engineer, a talented musician, and a dear friend.* [Read Dima's story](docs/memorial/MEMORIAL.md)

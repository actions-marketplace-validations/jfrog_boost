<p align="center">
  <a href="https://boost.jfrog.com/">
    <picture>
      <source srcset=".github/assets/boost-logo-dark.png" media="(prefers-color-scheme: dark)">
      <source srcset=".github/assets/boost-logo-light.png" media="(prefers-color-scheme: light)">
      <img src=".github/assets/boost-logo-light.png" alt="Boost" width="260">
    </picture>
  </a>
</p>

<p align="center">
  <strong>Tokens sparen. Kontext maximieren.</strong>
</p>

<p align="center">
  <sub>Intelligente Token-Einsparungen für Coding-Agents und Shell-Befehle.</sub>
</p>

<p align="center">
  <a href="https://boost.jfrog.com/"><img src="https://img.shields.io/badge/website-boost.jfrog.com-36a13b?logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxNiAxNiI%2BPHBhdGggZmlsbD0iIzlCRTE1RCIgZD0iTTkuMiAxLjUgMy4xIDkuMmgzLjlsLTEuMSA1LjMgNy4xLTguMkg5LjV6Ii8%2BPC9zdmc%2B" alt="Website"></a>
  <a href="https://github.com/jfrog/boost/releases"><img src="https://img.shields.io/github/v/release/jfrog/boost?color=36a13b" alt="Release"></a>
  <a href="https://go.dev/"><img src="https://img.shields.io/badge/go-1.25-00ADD8?logo=go&logoColor=white" alt="Go 1.25"></a>
  <img src="https://img.shields.io/badge/platform-linux%20%7C%20macOS%20%7C%20windows-lightgrey" alt="Platforms">
  <a href="https://github.com/jfrog/boost/releases"><img src="https://img.shields.io/github/downloads/jfrog/boost/total?color=6f42c1" alt="Downloads"></a>
  <a href="https://github.com/jfrog/boost/stargazers"><img src="https://img.shields.io/github/stars/jfrog/boost?style=flat&color=yellow" alt="Stars"></a><br>
  <img src="https://img.shields.io/badge/agent--native-brightgreen" alt="Agent-native">
  <img src="https://img.shields.io/badge/OpenTelemetry-enabled-blueviolet?logo=opentelemetry&logoColor=white" alt="OpenTelemetry">
</p>

<p align="center">
  <sub>Gesponsert von <a href="https://jfrog.com"><strong>JFrog</strong></a></sub>
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.es.md">Español</a> ·
  <a href="README.fr.md">Français</a> ·
  <strong>Deutsch</strong> ·
  <a href="README.ja.md">日本語</a> ·
  <a href="README.hi.md">हिन्दी</a> ·
  <a href="README.he.md">עברית</a>
</p>

---

<p align="center">
  <strong>Frogi, unser Maskottchen, erscheint, wenn du nur <code>boost</code> ausführst.</strong>
</p>

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-mascot-dark.png" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-mascot-light.png" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-mascot-light.png" alt="Frogi, the Boost mascot" width="180">
  </picture>
</p>

**Boost** umschließt die Befehle, die deine Agents bereits ausführen, und verwandelt laute Logs in kompakten, strukturierten Kontext, der das Signal behält — Fehler, Zeiten, Änderungszählungen, Cache-Treffer — und gleichzeitig das Rauschen reduziert.

Boost opfert nie Qualität für Einsparungen. Es entfernt nur, was sicher weggelassen werden kann, sodass die Agent-Ausgabe ebenso präzise bleibt. Unser [Terminal-Bench-2.0-Benchmark](https://boost.jfrog.com/blog/benchmarks-terminal-bench/) zeigt es: identische Erfolgsrate bei Aufgaben, ~12 % niedrigere Kosten — Boost hält Agents optimiert, ohne ihren Takt zu unterbrechen.

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-how-to-use-dark.gif" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-how-to-use-light.gif" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-how-to-use-light.gif" alt="Boost how to use: install, boost init, run a task, boost report" width="768">
  </picture>
</p>

## Schnellstart

**Boost installieren**

macOS / Linux / Windows WSL:

```bash
curl -fsSL https://boost.jfrog.com/install.sh | bash
```

Windows PowerShell:

```powershell
irm https://boost.jfrog.com/install.ps1 | iex
```

**In Cursor, Claude Code, GitHub Copilot und Codex CLI einbinden:**

```bash
boost init
```

Für KI-Coding-Agents, die Boost auf dem Rechner eines Nutzers installieren, folge **[AGENT-INSTALL.md](./AGENT-INSTALL.md)**.

## Wann du Boost nutzen solltest

- **Lange Coding-Agent-Sitzungen** — Halte den Kontext über Dutzende von Shell-Befehlen schlank, damit Agents Tokens für die Aufgabe ausgeben, nicht für die Scrollback-Historie.
- **Laute Test-, Build- und Debug-Schleifen** — Komprimiere `npm test`, `pytest`, `go test`, `docker build`, Linter und Logs und behalte dabei Fehlschläge und Zusammenfassungen.
- **CI-Pipelines** — Kürzere, leichter zu überblickende Job-Logs mit Timing- und Cache-Signalen für GitHub Actions und andere Runner.
- **Eigene oder interne Tools** — Füge TOML-Filter für deine eigenen CLIs hinzu, damit dieselbe Kompressionsschleife die Tools abdeckt, die deine Agents tatsächlich ausführen.

## Intelligente Token-Einsparungen

Boost kürzt die Ausgabe nicht einfach ab. Es wendet befehlsspezifische Filter an, die bewahren, was Agents brauchen, um über das Ergebnis nachzudenken.

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

Der Agent sieht die nützliche Zusammenfassung, nicht die Scrollback-Historie. Bei Fehlschlägen behält Boost den fehlgeschlagenen Test, den Compilerfehler oder den Stack-Frame, der zählt.

## [Wie Boost anders ist](https://boost.jfrog.com/docs/en/why-boost/)

| Fähigkeit | Boost | RTK | Headroom | Caveman |
| --- | :---: | :---: | :---: | :---: |
| Kompression der Befehlsausgabe | ✓ | ✓ | ✓ | × |
| Vollkontext- und RAG-Kompression | × | × | ✓ | × |
| Kompression der Assistentenantworten | × | × | × | ✓ |
| Wiederherstellung der Befehlsausgabe | ✓ | ✓ | ✓ | × |
| Native Freigabe sieht die Original-Executable | ✓ | × | — | — |
| Versioniertes Retrieval-Feedback | ✓ | × | × | × |
| Automatisches Deaktivieren wiederholt abgerufener Filter | ✓ | × | × | × |
| End-to-End-A/B zu Agent-Aufgabe + Kosten | ✓ | × | × | × |

## Sieh deine Einsparungen

Nach dem Umschließen von Befehlen öffne den interaktiven Web-Report:

```bash
boost report
```

Für eine narrative Zusammenfassung im Terminal:

```bash
boost report -t
# or: boost report --tui
```

## Was es umschließt

- **Agents:** Cursor, Claude Code, GitHub Copilot, Codex CLI.
- **Befehle:** Docker, npm, pytest, Git, GitHub CLI und andere Shell-Befehle laufen durch denselben Wrapper.

## Wie deine Agents Boost nutzen

- `boost docker build ...` — komprimiertes Build-Log und Layer-Cache-Zusammenfassung
- `boost npm ci` — Abhängigkeitszusammenfassung, lokaler Paket-Cache, retry-sichere Ausgabe
- `boost pytest` — ruhige Ausgabe bei grünen Läufen, nützliche Fehlschläge wenn Tests scheitern

## Aktualisieren

```bash
boost update
```

## Dokumentation

Siehe die [vollständige Dokumentation](https://boost.jfrog.com/docs/en/overview/) zu Befehlen, Konfiguration und OpenTelemetry-Export.

## Sicherheit & Datenschutz

- **Local-first.** Befehlsverlauf und Rohprotokolle bleiben auf deinem Rechner.
- **Nur Metadaten verlassen das System.** Wenn Boost Nutzungsdaten sendet, gehen sie nur an JFrog, um das Produkt zu verbessern. Exportierte Metadaten umfassen Timing, Exit-Code und Cache-Statistiken — niemals Rohprotokolle, Dateiinhalte oder Umgebungsvariablen. Secrets, die auf Muster wie `*_TOKEN`, `*_SECRET`, `AWS_*`, `DATABASE_URL` passen, werden vor dem Schreiben oder Export redigiert.
- **Offenes Protokoll, signierte Binaries.** OpenTelemetry-nativ. Binaries werden über GitHub Releases signiert ausgeliefert.

Vollständige Richtlinie, unterstützte Versionen und wie du eine Schwachstelle meldest: siehe [SECURITY.md](./SECURITY.md).

## Lizenz

Copyright © 2026 JFrog Ltd. Alle Rechte vorbehalten. Siehe [LICENSE](LICENSE) und [BETA_AGREEMENT.md](BETA_AGREEMENT.md).

---

*Gewidmet dem Andenken an Dima Gershovich — ein brillanter Ingenieur, ein talentierter Musiker und ein lieber Freund.* [Lies Dimas Geschichte](docs/memorial/MEMORIAL.md)

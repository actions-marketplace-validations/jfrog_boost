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
  <strong>Économisez des tokens. Maximisez le contexte.</strong>
</p>

<p align="center">
  <sub>Économies de tokens intelligentes pour les agents de codage et les commandes shell.</sub>
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
  <sub>Sponsorisé par <a href="https://jfrog.com"><strong>JFrog</strong></a></sub>
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.es.md">Español</a> ·
  <strong>Français</strong> ·
  <a href="README.de.md">Deutsch</a> ·
  <a href="README.ja.md">日本語</a> ·
  <a href="README.hi.md">हिन्दी</a> ·
  <a href="README.he.md">עברית</a>
</p>

---

<p align="center">
  <strong>Frogi, notre mascotte, apparaît lorsque vous exécutez simplement <code>boost</code>.</strong>
</p>

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-mascot-dark.png" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-mascot-light.png" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-mascot-light.png" alt="Frogi, the Boost mascot" width="180">
  </picture>
</p>

**Boost** encapsule les commandes que vos agents exécutent déjà, transformant des journaux bruyants en un contexte compact et structuré qui conserve le signal — erreurs, durées, nombres de changements, accès au cache — tout en réduisant le bruit.

Boost ne sacrifie jamais la qualité pour les économies. Il ne retire que ce qu'il est sûr de supprimer, afin que la sortie de l'agent reste aussi précise. Notre [benchmark Terminal-Bench 2.0](https://boost.jfrog.com/blog/benchmarks-terminal-bench/) le montre : même taux de réussite des tâches, ~12 % de coût en moins — Boost garde les agents optimisés sans jamais freiner leur rythme.

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-how-to-use-dark.gif" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-how-to-use-light.gif" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-how-to-use-light.gif" alt="Boost how to use: install, boost init, run a task, boost report" width="768">
  </picture>
</p>

## Démarrage rapide

**Installer Boost**

macOS / Linux / Windows WSL :

```bash
curl -fsSL https://boost.jfrog.com/install.sh | bash
```

Windows PowerShell :

```powershell
irm https://boost.jfrog.com/install.ps1 | iex
```

**Connectez-le à Cursor, Claude Code, GitHub Copilot et Codex CLI :**

```bash
boost init
```

Pour les agents de codage IA qui installent Boost sur la machine d'un utilisateur, suivez **[AGENT-INSTALL.md](./AGENT-INSTALL.md)**.

## Quand utiliser Boost

- **Longues sessions d'agents de codage** — Gardez le contexte léger sur des dizaines de commandes shell pour que les agents dépensent des tokens sur la tâche, pas sur l'historique de défilement.
- **Boucles bruyantes de test, de build et de debug** — Compressez `npm test`, `pytest`, `go test`, `docker build`, les linters et les journaux tout en conservant les échecs et les résumés.
- **Pipelines CI** — Journaux de jobs plus courts et plus faciles à parcourir, avec des signaux de durée et de cache pour GitHub Actions et d'autres runners.
- **Outils personnalisés ou internes** — Ajoutez des filtres TOML pour vos propres CLI afin que la même boucle de compression couvre les outils que vos agents utilisent réellement.

## Économies de tokens intelligentes

Boost ne se contente pas de tronquer la sortie. Il applique des filtres adaptés à la commande qui préservent ce dont les agents ont besoin pour raisonner sur le résultat.

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

L'agent voit le résumé utile, pas l'historique de défilement. En cas d'échec, Boost conserve le test en échec, l'erreur du compilateur ou la frame de pile qui compte.

## [En quoi Boost est différent](https://boost.jfrog.com/docs/en/why-boost/)

| Capacité | Boost | RTK | Headroom | Caveman |
| --- | :---: | :---: | :---: | :---: |
| Compression de la sortie des commandes | ✓ | ✓ | ✓ | × |
| Compression du contexte complet et RAG | × | × | ✓ | × |
| Compression des réponses de l'assistant | × | × | × | ✓ |
| Récupération de la sortie des commandes | ✓ | ✓ | ✓ | × |
| L'approbation native voit l'exécutable d'origine | ✓ | × | — | — |
| Feedback de récupération versionné | ✓ | × | × | × |
| Désactivation automatique des filtres récupérés de façon répétée | ✓ | × | × | × |
| A/B de bout en bout tâche d'agent + coût | ✓ | × | × | × |

## Voyez vos économies

Après avoir encapsulé des commandes, ouvrez le rapport web interactif :

```bash
boost report
```

Pour un résumé narratif dans le terminal :

```bash
boost report -t
# or: boost report --tui
```

## Ce qu'il encapsule

- **Agents :** Cursor, Claude Code, GitHub Copilot, Codex CLI.
- **Commandes :** Docker, npm, pytest, Git, GitHub CLI et d'autres commandes shell passent par le même wrapper.

## Comment vos agents utilisent Boost

- `boost docker build ...` — journal de build compressé et résumé du cache de couches
- `boost npm ci` — résumé des dépendances, cache local de paquets, sortie sûre pour les nouvelles tentatives
- `boost pytest` — sortie silencieuse sur les exécutions réussies, échecs utiles lorsque les tests cassent

## Mettre à jour

```bash
boost update
```

## Documentation

Consultez la [documentation complète](https://boost.jfrog.com/docs/en/overview/) pour les commandes, la configuration et l'export OpenTelemetry.

## Sécurité et confidentialité

- **Local d'abord.** L'historique des commandes et les journaux bruts restent sur votre machine.
- **Seules les métadonnées sortent.** Lorsque Boost envoie des données d'utilisation, elles vont uniquement à JFrog pour aider à améliorer le produit. Les métadonnées exportées incluent la durée, le code de sortie et les statistiques de cache, jamais les journaux bruts, le contenu des fichiers ou les valeurs d'environnement. Les secrets correspondant à des motifs comme `*_TOKEN`, `*_SECRET`, `AWS_*`, `DATABASE_URL` sont expurgés avant l'écriture ou l'export.
- **Protocole ouvert, binaires signés.** Natif OpenTelemetry. Les binaires sont publiés signés via GitHub Releases.

Politique complète, versions prises en charge et comment signaler une vulnérabilité : voir [SECURITY.md](./SECURITY.md).

## Licence

Copyright © 2026 JFrog Ltd. Tous droits réservés. Voir [LICENSE](LICENSE) et [BETA_AGREEMENT.md](BETA_AGREEMENT.md).

---

*Dédié à la mémoire de Dima Gershovich — un ingénieur brillant, un musicien talentueux et un cher ami.* [Lire l'histoire de Dima](docs/memorial/MEMORIAL.md)

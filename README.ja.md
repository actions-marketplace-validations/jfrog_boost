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
  <strong>トークンを節約。コンテキストを最大化。</strong>
</p>

<p align="center">
  <sub>コーディングエージェントとシェルコマンドのためのスマートなトークン節約。</sub>
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
  <sub>スポンサー: <a href="https://jfrog.com"><strong>JFrog</strong></a></sub>
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.es.md">Español</a> ·
  <a href="README.fr.md">Français</a> ·
  <a href="README.de.md">Deutsch</a> ·
  <strong>日本語</strong> ·
  <a href="README.hi.md">हिन्दी</a> ·
  <a href="README.he.md">עברית</a>
</p>

---

<p align="center">
  <strong>マスコットの Frogi は、<code>boost</code> だけを実行すると現れます。</strong>
</p>

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-mascot-dark.png" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-mascot-light.png" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-mascot-light.png" alt="Frogi, the Boost mascot" width="180">
  </picture>
</p>

**Boost** は、エージェントがすでに実行しているコマンドをラップし、ノイズの多いログを、エラー・タイミング・変更数・キャッシュヒットというシグナルを保ちつつノイズを削減した、コンパクトで構造化されたコンテキストに変えます。

Boost は節約のために品質を犠牲にしません。安全に削除できるものだけを削るので、エージェントの出力は同じように鋭いままです。[Terminal-Bench 2.0 ベンチマーク](https://boost.jfrog.com/blog/benchmarks-terminal-bench/)がそれを示しています。タスクの成功率は同じで、コストは約 12% 低下 — Boost はエージェントの歩みを崩すことなく最適化を保ちます。

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-how-to-use-dark.gif" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-how-to-use-light.gif" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-how-to-use-light.gif" alt="Boost how to use: install, boost init, run a task, boost report" width="768">
  </picture>
</p>

## クイックスタート

**Boost をインストール**

macOS / Linux / Windows WSL:

```bash
curl -fsSL https://boost.jfrog.com/install.sh | bash
```

Windows PowerShell:

```powershell
irm https://boost.jfrog.com/install.ps1 | iex
```

**Cursor、Claude Code、GitHub Copilot、Codex CLI に接続:**

```bash
boost init
```

ユーザーのマシンに Boost をインストールする AI コーディングエージェント向けには、**[AGENT-INSTALL.md](./AGENT-INSTALL.md)** に従ってください。

## Boost を使うタイミング

- **長いコーディングエージェントセッション** — 数十のシェルコマンドにわたってコンテキストをスリムに保ち、エージェントがスクロールバックではなくタスクにトークンを使えるようにします。
- **ノイズの多いテスト・ビルド・デバッグのループ** — `npm test`、`pytest`、`go test`、`docker build`、リンター、ログを圧縮しつつ、失敗と要約は保持します。
- **CI パイプライン** — GitHub Actions やその他のランナー向けに、タイミングとキャッシュのシグナル付きで、短く読みやすいジョブログを提供します。
- **カスタムまたは社内ツール** — 独自 CLI 向けの TOML フィルタを追加し、エージェントが実際に使うツールにも同じ圧縮ループを適用します。

## スマートなトークン節約

Boost は出力を単に切り詰めるだけではありません。結果についてエージェントが推論するために必要なものを保つ、コマンド対応のフィルタを適用します。

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

エージェントはスクロールバックではなく、有用な要約を見ます。失敗時には、Boost は失敗したテスト、コンパイラエラー、または重要なスタックフレームを保持します。

## [Boost の違い](https://boost.jfrog.com/docs/en/why-boost/)

| 機能 | Boost | RTK | Headroom | Caveman |
| --- | :---: | :---: | :---: | :---: |
| コマンド出力の圧縮 | ✓ | ✓ | ✓ | × |
| フルコンテキストと RAG の圧縮 | × | × | ✓ | × |
| アシスタント応答の圧縮 | × | × | × | ✓ |
| コマンド出力の復元 | ✓ | ✓ | ✓ | × |
| ネイティブ承認が元の実行ファイルを見る | ✓ | × | — | — |
| バージョン付き検索フィードバック | ✓ | × | × | × |
| 繰り返し復元されたフィルタの自動無効化 | ✓ | × | × | × |
| エージェントタスク + コストのエンドツーエンド A/B | ✓ | × | × | × |

## 節約を確認する

コマンドをラップしたあと、対話型の Web レポートを開きます。

```bash
boost report
```

ターミナルでのナラティブ要約の場合:

```bash
boost report -t
# or: boost report --tui
```

## ラップ対象

- **エージェント:** Cursor、Claude Code、GitHub Copilot、Codex CLI。
- **コマンド:** Docker、npm、pytest、Git、GitHub CLI、およびその他のシェルコマンドが同じラッパーを通ります。

## エージェントが Boost を使う様子

- `boost docker build ...` — 圧縮されたビルドログとレイヤーキャッシュの要約
- `boost npm ci` — 依存関係の要約、ローカルパッケージキャッシュ、再試行に安全な出力
- `boost pytest` — 成功時は静かな出力、テスト失敗時は有用な失敗情報

## 更新

```bash
boost update
```

## ドキュメント

コマンド、設定、OpenTelemetry エクスポートについては、[完全なドキュメント](https://boost.jfrog.com/docs/en/overview/)を参照してください。

## セキュリティとプライバシー

- **ローカル優先。** コマンド履歴と生のログはマシン上に残ります。
- **出ていくのはメタデータのみ。** Boost が使用データを送信する場合、製品改善のために JFrog にのみ送られます。エクスポートされるメタデータにはタイミング、終了コード、キャッシュ統計が含まれ、生のログ、ファイル内容、環境変数の値は含まれません。`*_TOKEN`、`*_SECRET`、`AWS_*`、`DATABASE_URL` などのパターンに一致するシークレットは、書き込みまたはエクスポートの前に編集されます。
- **オープンプロトコル、署名付きバイナリ。** OpenTelemetry ネイティブ。バイナリは GitHub Releases 経由で署名されて配布されます。

完全なポリシー、サポートされるバージョン、脆弱性の報告方法: [SECURITY.md](./SECURITY.md) を参照してください。

## ライセンス

Copyright © 2026 JFrog Ltd. All rights reserved. [LICENSE](LICENSE) および [BETA_AGREEMENT.md](BETA_AGREEMENT.md) を参照してください。

---

*Dima Gershovich の思い出に捧ぐ — 優れたエンジニア、才能ある音楽家、そして親愛なる友人。* [Dima の物語を読む](docs/memorial/MEMORIAL.md)

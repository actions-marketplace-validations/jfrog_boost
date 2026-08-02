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
  <strong>Ahorra tokens. Maximiza el contexto.</strong>
</p>

<p align="center">
  <sub>Ahorro inteligente de tokens para agentes de codificación y comandos de shell.</sub>
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
  <sub>Patrocinado por <a href="https://jfrog.com"><strong>JFrog</strong></a></sub>
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <strong>Español</strong> ·
  <a href="README.fr.md">Français</a> ·
  <a href="README.de.md">Deutsch</a> ·
  <a href="README.ja.md">日本語</a> ·
  <a href="README.hi.md">हिन्दी</a> ·
  <a href="README.he.md">עברית</a>
</p>

---

<p align="center">
  <strong>Frogi, nuestra mascota, aparece cuando ejecutas solo <code>boost</code>.</strong>
</p>

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-mascot-dark.png" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-mascot-light.png" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-mascot-light.png" alt="Frogi, the Boost mascot" width="180">
  </picture>
</p>

**Boost** envuelve los comandos que tus agentes ya ejecutan, convirtiendo logs ruidosos en contexto compacto y estructurado que conserva la señal — errores, tiempos, conteos de cambios, aciertos de caché — mientras reduce el ruido.

Boost nunca sacrifica calidad por ahorro. Solo recorta lo que es seguro eliminar, para que la salida del agente siga siendo igual de precisa. Nuestro [benchmark Terminal-Bench 2.0](https://boost.jfrog.com/blog/benchmarks-terminal-bench/) lo demuestra: la misma tasa de éxito en las tareas, ~12 % menos de coste — Boost mantiene a los agentes optimizados sin frenar su ritmo.

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-how-to-use-dark.gif" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-how-to-use-light.gif" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-how-to-use-light.gif" alt="Boost how to use: install, boost init, run a task, boost report" width="768">
  </picture>
</p>

## Inicio rápido

**Instalar Boost**

macOS / Linux / Windows WSL:

```bash
curl -fsSL https://boost.jfrog.com/install.sh | bash
```

Windows PowerShell:

```powershell
irm https://boost.jfrog.com/install.ps1 | iex
```

**Conéctalo a Cursor, Claude Code, GitHub Copilot y Codex CLI:**

```bash
boost init
```

Para agentes de codificación con IA que instalen Boost en la máquina de un usuario, sigue **[AGENT-INSTALL.md](./AGENT-INSTALL.md)**.

## Cuándo usar Boost

- **Sesiones largas de agentes de codificación** — Mantén el contexto ágil a lo largo de docenas de comandos de shell para que los agentes gasten tokens en la tarea, no en el scrollback.
- **Bucles ruidosos de test, build y debug** — Comprime `npm test`, `pytest`, `go test`, `docker build`, linters y logs, conservando fallos y resúmenes.
- **Pipelines de CI** — Logs de jobs más cortos y fáciles de escanear, con señales de tiempo y de caché para GitHub Actions y otros runners.
- **Herramientas personalizadas o internas** — Añade filtros TOML para tus propios CLIs y así el mismo bucle de compresión cubre las herramientas que tus agentes realmente usan.

## Ahorro inteligente de tokens

Boost no se limita a truncar la salida. Aplica filtros conscientes del comando que preservan lo que los agentes necesitan para razonar sobre el resultado.

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

El agente ve el resumen útil, no el scrollback. En caso de fallo, Boost conserva el test fallido, el error del compilador o el frame de stack que importa.

## [Cómo se diferencia Boost](https://boost.jfrog.com/docs/en/why-boost/)

| Capacidad | Boost | RTK | Headroom | Caveman |
| --- | :---: | :---: | :---: | :---: |
| Compresión de salida de comandos | ✓ | ✓ | ✓ | × |
| Compresión de contexto completo y RAG | × | × | ✓ | × |
| Compresión de respuestas del asistente | × | × | × | ✓ |
| Recuperación de salida de comandos | ✓ | ✓ | ✓ | × |
| La aprobación nativa ve el ejecutable original | ✓ | × | — | — |
| Feedback de recuperación versionado | ✓ | × | × | × |
| Desactivar automáticamente filtros recuperados de forma repetida | ✓ | × | × | × |
| A/B de tarea de agente + coste de extremo a extremo | ✓ | × | × | × |

## Consulta tus ahorros

Tras envolver comandos, abre el informe web interactivo:

```bash
boost report
```

Para un resumen narrativo en la terminal:

```bash
boost report -t
# or: boost report --tui
```

## Qué envuelve

- **Agentes:** Cursor, Claude Code, GitHub Copilot, Codex CLI.
- **Comandos:** Docker, npm, pytest, Git, GitHub CLI y otros comandos de shell pasan por el mismo wrapper.

## Cómo usan Boost tus agentes

- `boost docker build ...` — log de build comprimido y resumen de caché de capas
- `boost npm ci` — resumen de dependencias, caché local de paquetes, salida segura para reintentos
- `boost pytest` — salida silenciosa en ejecuciones en verde, fallos útiles cuando fallan los tests

## Actualizar

```bash
boost update
```

## Documentación

Consulta la [documentación completa](https://boost.jfrog.com/docs/en/overview/) para comandos, configuración y exportación OpenTelemetry.

## Seguridad y privacidad

- **Local primero.** El historial de comandos y los logs en bruto permanecen en tu máquina.
- **Solo salen metadatos.** Cuando Boost envía datos de uso, van únicamente a JFrog para ayudar a mejorar el producto. Los metadatos exportados incluyen tiempos, código de salida y estadísticas de caché; nunca logs en bruto, contenido de archivos ni valores de entorno. Los secretos que coinciden con patrones como `*_TOKEN`, `*_SECRET`, `AWS_*`, `DATABASE_URL` se redactan antes de escribir o exportar.
- **Protocolo abierto, binarios firmados.** Nativo de OpenTelemetry. Los binarios se publican firmados a través de GitHub Releases.

Política completa, versiones compatibles y cómo informar de una vulnerabilidad: consulta [SECURITY.md](./SECURITY.md).

## Licencia

Copyright © 2026 JFrog Ltd. Todos los derechos reservados. Consulta [LICENSE](LICENSE) y [BETA_AGREEMENT.md](BETA_AGREEMENT.md).

---

*Dedicado a la memoria de Dima Gershovich — un ingeniero brillante, un músico talentoso y un querido amigo.* [Lee la historia de Dima](docs/memorial/MEMORIAL.md)

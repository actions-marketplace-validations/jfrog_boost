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
  <strong>חסכו בטוקנים. ממקסמו את ההקשר.</strong>
</p>

<p align="center">
  <sub>חיסכון חכם בטוקנים לסוכני קוד ולפקודות shell.</sub>
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
  <sub>בחסות <a href="https://jfrog.com"><strong>JFrog</strong></a></sub>
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.es.md">Español</a> ·
  <a href="README.fr.md">Français</a> ·
  <a href="README.de.md">Deutsch</a> ·
  <a href="README.ja.md">日本語</a> ·
  <a href="README.hi.md">हिन्दी</a> ·
  <strong>עברית</strong>
</p>

---

<p align="center">
  <strong>Frogi, הקמע שלנו, מופיע כשמריצים רק <code>boost</code>.</strong>
</p>

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-mascot-dark.png" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-mascot-light.png" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-mascot-light.png" alt="Frogi, the Boost mascot" width="180">
  </picture>
</p>

**Boost** עוטף את הפקודות שסוכניכם כבר מריצים, והופך לוגים רועשים להקשר קומפקטי ומבני ששומר על האות — שגיאות, זמנים, מספרי שינויים, פגיעות מטמון — תוך צמצום הרעש.

Boost לעולם אינו מוותר על איכות למען חיסכון. הוא גוזם רק את מה שבטוח להסיר, כך שפלט הסוכן נשאר חד כמו קודם. ה[בנצ'מרק Terminal-Bench 2.0](https://boost.jfrog.com/blog/benchmarks-terminal-bench/) שלנו מראה זאת: שיעור הצלחה זהה במשימות, עלות נמוכה בכ־12% — Boost שומר על הסוכנים ממוטבים מבלי לשבור את הקצב.

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-how-to-use-dark.gif" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-how-to-use-light.gif" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-how-to-use-light.gif" alt="Boost how to use: install, boost init, run a task, boost report" width="768">
  </picture>
</p>

## התחלה מהירה

**התקנת Boost**

macOS / Linux / Windows WSL:

```bash
curl -fsSL https://boost.jfrog.com/install.sh | bash
```

Windows PowerShell:

```powershell
irm https://boost.jfrog.com/install.ps1 | iex
```

**חברו אותו ל-Cursor, Claude Code, GitHub Copilot ו-Codex CLI:**

```bash
boost init
```

עבור סוכני קוד מבוססי AI שמתקינים את Boost במחשב של משתמש, עקבו אחר **[AGENT-INSTALL.md](./AGENT-INSTALL.md)**.

## מתי להשתמש ב-Boost

- **סשנים ארוכים של סוכני קוד** — שמרו על הקשר רזה לאורך עשרות פקודות shell כדי שהסוכנים יוציאו טוקנים על המשימה, לא על היסטוריית הגלילה.
- **לולאות רועשות של בדיקות, בנייה ודיבוג** — דחסו `npm test`, `pytest`, `go test`, `docker build`, linters ולוגים תוך שמירה על כשלים וסיכומים.
- **צינורות CI** — לוגי משימות קצרים וקלים יותר לסריקה, עם אותות תזמון ומטמון עבור GitHub Actions ו-runners אחרים.
- **כלים מותאמים או פנימיים** — הוסיפו מסנני TOML ל-CLI שלכם כך שאותה לולאת דחיסה תכסה את הכלים שסוכניכם באמת מריצים.

## חיסכון חכם בטוקנים

Boost אינו רק מקצץ את הפלט. הוא מחיל מסננים מודעי-פקודה ששומרים על מה שהסוכנים צריכים כדי להסיק מסקנות לגבי התוצאה.

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

הסוכן רואה את הסיכום השימושי, לא את היסטוריית הגלילה. בכשלים, Boost שומר את הבדיקה שנכשלה, את שגיאת המהדר או את מסגרת ה-stack שחשובה.

## [במה Boost שונה](https://boost.jfrog.com/docs/en/why-boost/)

| יכולת | Boost | RTK | Headroom | Caveman |
| --- | :---: | :---: | :---: | :---: |
| דחיסת פלט פקודות | ✓ | ✓ | ✓ | × |
| דחיסת הקשר מלא ו-RAG | × | × | ✓ | × |
| דחיסת תשובות העוזר | × | × | × | ✓ |
| שחזור פלט פקודות | ✓ | ✓ | ✓ | × |
| אישור מקורי רואה את הקובץ המקורי להרצה | ✓ | × | — | — |
| משוב שחזור מגרסאות | ✓ | × | × | × |
| השבתה אוטומטית של מסננים שנשלפו שוב ושוב | ✓ | × | × | × |
| A/B מקצה לקצה של משימת סוכן + עלות | ✓ | × | × | × |

## ראו את החיסכון שלכם

לאחר עטיפת פקודות, פתחו את דוח האינטרנט האינטראקטיבי:

```bash
boost report
```

לסיכום נרטיבי בטרמינל:

```bash
boost report -t
# or: boost report --tui
```

## מה הוא עוטף

- **סוכנים:** Cursor, Claude Code, GitHub Copilot, Codex CLI.
- **פקודות:** Docker, npm, pytest, Git, GitHub CLI ופקודות shell אחרות עוברות באותו wrapper.

## איך הסוכנים שלכם משתמשים ב-Boost

- `boost docker build ...` — לוג בנייה דחוס וסיכום מטמון שכבות
- `boost npm ci` — סיכום תלויות, מטמון חבילות מקומי, פלט בטוח לניסיונות חוזרים
- `boost pytest` — פלט שקט בהרצות ירוקות, כשלים שימושיים כשבדיקות נשברות

## עדכון

```bash
boost update
```

## תיעוד

ראו את ה[תיעוד המלא](https://boost.jfrog.com/docs/en/overview/) לפקודות, תצורה וייצוא OpenTelemetry.

## אבטחה ופרטיות

- **מקומי תחילה.** היסטוריית הפקודות והלוגים הגולמיים נשארים במחשב שלכם.
- **רק מטא-נתונים יוצאים.** כש-Boost שולח נתוני שימוש, הם מגיעים רק ל-JFrog כדי לסייע בשיפור המוצר. מטא-נתונים מיוצאים כוללים תזמון, קוד יציאה וסטטיסטיקות מטמון — לעולם לא לוגים גולמיים, תוכן קבצים או ערכי סביבה. סודות התואמים לתבניות כמו `*_TOKEN`, `*_SECRET`, `AWS_*`, `DATABASE_URL` מוסתרים לפני כתיבה או ייצוא.
- **פרוטוקול פתוח, בינאריים חתומים.** מותאם ל-OpenTelemetry. הבינאריים מגיעים חתומים דרך GitHub Releases.

מדיניות מלאה, גרסאות נתמכות וכיצד לדווח על פגיעוּת: ראו [SECURITY.md](./SECURITY.md).

## רישיון

Copyright © 2026 JFrog Ltd. כל הזכויות שמורות. ראו [LICENSE](LICENSE) ו-[BETA_AGREEMENT.md](BETA_AGREEMENT.md).

---

*מוקדש לזכרו של דימה גרשוביץ' — מהנדס מבריק, מוזיקאי מוכשר וחבר יקר.* [קראו את סיפורו של דימה](docs/memorial/MEMORIAL.md)

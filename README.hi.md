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
  <strong>टोकन बचाएँ। कॉन्टेक्स्ट को अधिकतम करें।</strong>
</p>

<p align="center">
  <sub>कोडिंग एजेंट्स और शेल कमांड के लिए स्मार्ट टोकन बचत।</sub>
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
  <sub>प्रायोजक: <a href="https://jfrog.com"><strong>JFrog</strong></a></sub>
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.es.md">Español</a> ·
  <a href="README.fr.md">Français</a> ·
  <a href="README.de.md">Deutsch</a> ·
  <a href="README.ja.md">日本語</a> ·
  <strong>हिन्दी</strong> ·
  <a href="README.he.md">עברית</a>
</p>

---

<p align="center">
  <strong>हमारा शुभंकर Frogi तब प्रकट होता है जब आप केवल <code>boost</code> चलाते हैं।</strong>
</p>

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-mascot-dark.png" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-mascot-light.png" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-mascot-light.png" alt="Frogi, the Boost mascot" width="180">
  </picture>
</p>

**Boost** उन कमांड को रैप करता है जिन्हें आपके एजेंट पहले से चलाते हैं, शोरगुल भरे लॉग को कॉम्पैक्ट, संरचित कॉन्टेक्स्ट में बदलता है जो सिग्नल — त्रुटियाँ, समय, परिवर्तन गणना, कैश हिट — रखता है और शोर कम करता है।

Boost कभी बचत के लिए गुणवत्ता का सौदा नहीं करता। यह केवल वही काटता है जिसे सुरक्षित रूप से हटाया जा सकता है, ताकि एजेंट आउटपुट उतना ही तेज़ बना रहे। हमारा [Terminal-Bench 2.0 बेंचमार्क](https://boost.jfrog.com/blog/benchmarks-terminal-bench/) यही दिखाता है: समान टास्क पास दर, ~12% कम लागत — Boost एजेंट्स को बिना उनकी गति तोड़े अनुकूलित रखता है।

<p align="center">
  <picture>
    <source srcset=".github/assets/boost-how-to-use-dark.gif" media="(prefers-color-scheme: dark)">
    <source srcset=".github/assets/boost-how-to-use-light.gif" media="(prefers-color-scheme: light)">
    <img src=".github/assets/boost-how-to-use-light.gif" alt="Boost how to use: install, boost init, run a task, boost report" width="768">
  </picture>
</p>

## त्वरित शुरुआत

**Boost इंस्टॉल करें**

macOS / Linux / Windows WSL:

```bash
curl -fsSL https://boost.jfrog.com/install.sh | bash
```

Windows PowerShell:

```powershell
irm https://boost.jfrog.com/install.ps1 | iex
```

**इसे Cursor, Claude Code, GitHub Copilot और Codex CLI से जोड़ें:**

```bash
boost init
```

उपयोगकर्ता की मशीन पर Boost इंस्टॉल करने वाले AI कोडिंग एजेंट्स के लिए **[AGENT-INSTALL.md](./AGENT-INSTALL.md)** का पालन करें।

## Boost कब उपयोग करें

- **लंबे कोडिंग-एजेंट सत्र** — दर्जनों शेल कमांड में कॉन्टेक्स्ट को दुबला रखें ताकि एजेंट स्क्रॉलबैक पर नहीं, टास्क पर टोकन खर्च करें।
- **शोरगुल भरे टेस्ट, बिल्ड और डिबग लूप** — `npm test`, `pytest`, `go test`, `docker build`, लिंटर्स और लॉग को संपीड़ित करें, विफलताओं और सारांशों को बनाए रखते हुए।
- **CI पाइपलाइन** — GitHub Actions और अन्य रनर्स के लिए समय और कैश सिग्नल के साथ छोटे, स्कैन करने में आसान जॉब लॉग।
- **कस्टम या आंतरिक टूल** — अपने CLI के लिए TOML फ़िल्टर जोड़ें ताकि वही संपीड़न लूप उन टूल्स को कवर करे जिन्हें आपके एजेंट वास्तव में चलाते हैं।

## स्मार्ट टोकन बचत

Boost केवल आउटपुट को काटता नहीं है। यह कमांड-जागरूक फ़िल्टर लागू करता है जो वह सुरक्षित रखते हैं जिसकी एजेंट्स को परिणाम पर तर्क करने के लिए आवश्यकता होती है।

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

एजेंट स्क्रॉलबैक नहीं, उपयोगी सारांश देखता है। विफलताओं पर, Boost वह विफल टेस्ट, कंपाइलर त्रुटि, या स्टैक फ्रेम रखता है जो मायने रखता है।

## [Boost कैसे अलग है](https://boost.jfrog.com/docs/en/why-boost/)

| क्षमता | Boost | RTK | Headroom | Caveman |
| --- | :---: | :---: | :---: | :---: |
| कमांड आउटपुट संपीड़न | ✓ | ✓ | ✓ | × |
| पूर्ण-कॉन्टेक्स्ट और RAG संपीड़न | × | × | ✓ | × |
| सहायक उत्तर संपीड़न | × | × | × | ✓ |
| कमांड आउटपुट पुनर्प्राप्ति | ✓ | ✓ | ✓ | × |
| नेटिव अनुमोदन मूल एक्ज़ीक्यूटेबल देखता है | ✓ | × | — | — |
| वर्शन्ड पुनर्प्राप्ति फ़ीडबैक | ✓ | × | × | × |
| बार-बार पुनर्प्राप्त फ़िल्टर स्वतः अक्षम करें | ✓ | × | × | × |
| एंड-टू-एंड एजेंट टास्क + लागत A/B | ✓ | × | × | × |

## अपनी बचत देखें

कमांड रैप करने के बाद, इंटरैक्टिव वेब रिपोर्ट खोलें:

```bash
boost report
```

टर्मिनल नैरेटिव सारांश के लिए:

```bash
boost report -t
# or: boost report --tui
```

## यह क्या रैप करता है

- **एजेंट्स:** Cursor, Claude Code, GitHub Copilot, Codex CLI।
- **कमांड:** Docker, npm, pytest, Git, GitHub CLI, और अन्य शेल कमांड उसी रैपर से गुज़रते हैं।

## आपके एजेंट Boost कैसे उपयोग करते हैं

- `boost docker build ...` — संपीड़ित बिल्ड लॉग और लेयर-कैश सारांश
- `boost npm ci` — निर्भरता सारांश, स्थानीय पैकेज कैश, पुनः प्रयास-सुरक्षित आउटपुट
- `boost pytest` — हरी रन पर शांत आउटपुट, टेस्ट टूटने पर उपयोगी विफलताएँ

## अपडेट

```bash
boost update
```

## दस्तावेज़ीकरण

कमांड, कॉन्फ़िगरेशन और OpenTelemetry एक्सपोर्ट के लिए [पूर्ण दस्तावेज़ीकरण](https://boost.jfrog.com/docs/en/overview/) देखें।

## सुरक्षा और गोपनीयता

- **लोकल-फर्स्ट।** कमांड इतिहास और कच्चे लॉग आपकी मशीन पर रहते हैं।
- **केवल मेटाडेटा बाहर जाता है।** जब Boost उपयोग डेटा भेजता है, तो वह उत्पाद सुधारने में मदद के लिए केवल JFrog को जाता है। निर्यात किए गए मेटाडेटा में समय, एग्ज़िट कोड और कैश आँकड़े शामिल हैं — कभी कच्चे लॉग, फ़ाइल सामग्री या एन्व मान नहीं। `*_TOKEN`, `*_SECRET`, `AWS_*`, `DATABASE_URL` जैसे पैटर्न से मेल खाने वाले सीक्रेट्स लेखन या निर्यात से पहले रिडैक्ट कर दिए जाते हैं।
- **ओपन प्रोटोकॉल, हस्ताक्षरित बाइनरी।** OpenTelemetry-नेटिव। बाइनरी GitHub Releases के माध्यम से हस्ताक्षरित होकर आती हैं।

पूर्ण नीति, समर्थित संस्करण, और भेद्यता की रिपोर्ट कैसे करें: [SECURITY.md](./SECURITY.md) देखें।

## लाइसेंस

Copyright © 2026 JFrog Ltd. सर्वाधिकार सुरक्षित। [LICENSE](LICENSE) और [BETA_AGREEMENT.md](BETA_AGREEMENT.md) देखें।

---

*Dima Gershovich की स्मृति को समर्पित — एक प्रतिभाशाली इंजीनियर, एक प्रतिभाशाली संगीतकार, और एक प्रिय मित्र।* [Dima की कहानी पढ़ें](docs/memorial/MEMORIAL.md)

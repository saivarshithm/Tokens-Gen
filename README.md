# 🤖 Tokens-Gen

<div align="center">

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Puppeteer](https://img.shields.io/badge/Puppeteer-40B5A4?style=for-the-badge&logo=googlechrome&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)
![Version](https://img.shields.io/badge/Version-1.0.0-orange?style=for-the-badge)

**A Discord token generator powered by Puppeteer, 2Captcha, and stealth automation.**

> ⚠️ **For educational purposes only.** The author is not responsible for any misuse of this tool.

</div>

---

## 📖 Overview

Tokens-Gen automates the Discord account creation process using a headless browser. It handles temporary email generation, form filling, CAPTCHA solving, and email verification — outputting a full `email:username:password:token` credential set per run.

---

## ✨ Features

- 🕵️ **Stealth browsing** — Uses `puppeteer-extra-plugin-stealth` to avoid bot detection
- 🧩 **Auto CAPTCHA solving** — Integrates with [2Captcha](https://2captcha.com/) for reCAPTCHA bypass
- 📧 **Temporary email** — Generates disposable inboxes via [temp-mail.org](https://temp-mail.org/)
- 🔀 **Proxy support** — Routes traffic through a configurable residential rotating proxy
- 🛡️ **Ad & tracker blocking** — Uses `@cliqz/adblocker-puppeteer` during mail verification
- 📝 **Logging** — Writes timestamped logs to `stdout.log` / `stderr.log` and saves accounts to `accounts.txt`
- 🔁 **Loop mode** — `start.bat` continuously re-runs the generator

---

## ⚙️ Requirements

| Requirement | Details |
|---|---|
| **Node.js** | v14 or higher |
| **2Captcha API key** | [Get one here](https://2captcha.com/) |
| **Residential rotating proxy** | Required to avoid IP bans |

---

## 🚀 Installation

```bash
# 1. Clone the repository
git clone https://github.com/Just-Msv/Tokens-Gen.git
cd Tokens-Gen

# 2. Install dependencies
npm install
```

---

## 🔧 Configuration

Open `gen.js` and fill in your credentials at the top of the file:

```js
// Settings
const captchakey = 'YOUR_2CAPTCHA_API_KEY';
const PROXY_ADDR = 'host:port';           // e.g. 'proxy.example.com:8080'
const PROXY_USERNAME = 'proxy_user';
const PROXY_PASSWORD = 'proxy_pass';
```

---

## ▶️ Usage

### Single run

```bash
node gen.js
```

### Continuous loop (Windows)

```bat
start.bat
```

> `start.bat` loops `node gen` indefinitely, generating one account per iteration.

---

## 📂 Output

Generated credentials are appended to `accounts.txt` in the following format:

```
email:username:password:token
```

Runtime logs are written to:
- `stdout.log` — general info
- `stderr.log` — errors

---

## 📦 Dependencies

| Package | Purpose |
|---|---|
| `puppeteer-extra` | Extended Puppeteer with plugin support |
| `puppeteer-extra-plugin-stealth` | Evades headless browser detection |
| `puppeteer-extra-plugin-recaptcha` | Solves reCAPTCHA via 2Captcha |
| `@cliqz/adblocker-puppeteer` | Blocks ads and trackers |
| `unique-names-generator` | Generates random usernames |
| `cross-fetch` | Fetch API for Node.js |

---

## ⚠️ Disclaimer

This project is intended **strictly for educational and research purposes**. Using this tool to violate [Discord's Terms of Service](https://discord.com/terms) is prohibited. The author assumes **no liability** for any actions taken using this software.

---

## 📄 License

Released under the [MIT License](./LICENSE)
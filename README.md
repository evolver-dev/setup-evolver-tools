# 🛠️ setup-evolver-tools

> **Install 254+ zero-dependency CLI tools in your GitHub Actions CI pipeline — in seconds.**

[![Marketplace](https://img.shields.io/badge/GitHub-Marketplace-6f42c1?logo=github)](https://github.com/marketplace/actions/setup-evolver-tools)
[![Version](https://img.shields.io/github/v/release/evolver-dev/setup-evolver-tools?logo=github)](https://github.com/evolver-dev/setup-evolver-tools/releases)
[![evolver-tools](https://img.shields.io/badge/evolver--tools-254%2B%20tools-brightgreen?logo=python)](https://github.com/evolver-dev/evolver-tools)

---

## ✨ What is this?

This Action installs [evolver-tools](https://github.com/evolver-dev/evolver-tools) — the largest collection of zero-dependency CLI tools for developers. After setup, every `evtool <command>` is available in your workflow.

**No apt-get. No npm. No cargo. Just `pip install` in 5 seconds.**

---

## 🚀 Quick Start

```yaml
jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: evolver-dev/setup-evolver-tools@v1
      - name: Validate all configs
        run: |
          evtool json-validate config.json
          evtool envcheck .env.example
          evtool markdown-check README.md
```

---

## 📋 What you get

| Category | Tools |
|----------|-------|
| **CSV/Data** | csv-stats, csv-validate, csv-to-json, csv-to-markdown, csv-sort |
| **JSON** | json-pretty, json-validate, json-merge, json-to-yaml |
| **Encoding** | base64, url-encode, html-encode, hex-dump, rot13 |
| **DevOps** | siege-lite (load test), envcheck, license-cli, cron-pretty |
| **System** | sysmon (TUI monitor), project-doctor, process-analyzer |
| **Text** | markdown-check, text-stats, diff-cmd, line-counter, uniq-lines |
| **Crypto** | hash-file, gen-password, random-uuid, entropy-check |
| **Fun** | ascii-banner, cowsay, emoji-cli, figlet-fonts, dice-roll |
| **Network** | http-status, ip-info, port-check, dns-lookup, whois-cli |
| **And more...** | 254+ tools in total |

---

## 🔧 Advanced: Pin a Version

```yaml
- uses: evolver-dev/setup-evolver-tools@v1
  with:
    version: '38.0.3'   # defaults to latest
```

---

## 💡 Why use this in CI?

- **Zero dependency conflicts** — pure Python stdlib, no extra packages
- **Lightning fast** — installs in <5 seconds
- **254+ tools** — replaces dozens of separate install steps
- **Works offline** — once cached, no network needed
- **Pipe-friendly** — `cat data.csv | evtool csv-stats --histogram amount`

---

## 📦 Pipeline Examples

### Data QA Pipeline
```yaml
- uses: evolver-dev/setup-evolver-tools@v1
- run: |
    evtool csv-stats --all uploads.csv
    evtool csv-validate --schema schema.json uploads.csv
    evtool json-validate response.json
```

### Code Quality Gate
```yaml
- uses: evolver-dev/setup-evolver-tools@v1
- run: |
    evtool project-doctor . --min-score 7
    evtool markdown-check docs/*.md
    evtool envcheck .env.production --strict
```

---

## 🔗 Links

- [evolver-tools](https://github.com/evolver-dev/evolver-tools) — the full toolkit
- [Website & Docs](https://evolver-dev.github.io/evolver-tools/)
- [PyPI](https://pypi.org/project/evolver-tools/)

## 📄 License

MIT

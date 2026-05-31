# setup-evolver-tools

GitHub Action to install [evolver-tools](https://github.com/evolver-dev/evolver-tools) — 254+ zero-dependency CLI tools — in your CI pipeline.

## Usage

```yaml
steps:
  - uses: evolver-dev/setup-evolver-tools@v1
```

After this step, all 254+ `evtool` commands are available:

```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: evolver-dev/setup-evolver-tools@v1
      - name: Analyze CSV
        run: evtool csv-stats data.csv
      - name: Validate JSON
        run: evtool json-validate config.json
```

## Pin a specific version

```yaml
- uses: evolver-dev/setup-evolver-tools@v1
  with:
    version: '38.0.2'
```

## Why evolver-tools in CI?

- **Zero dependencies** — installs in seconds, no version conflicts
- **254+ tools** — CSV, JSON, text, encoding, crypto, sysadmin, networking, and more
- **Pure Python stdlib** — works offline, no npm/cargo/apt installs needed
- **Pipe-friendly** — `cat data.csv | evtool csv-stats --histogram amount`

## License

MIT

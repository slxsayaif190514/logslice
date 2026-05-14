# logslice

> Command-line utility to extract and filter log segments by time range, level, or regex pattern with streaming support.

---

## Installation

```bash
pip install logslice
```

Or install from source:

```bash
git clone https://github.com/yourname/logslice.git && cd logslice && pip install .
```

---

## Usage

```bash
# Filter by time range
logslice --start "2024-01-15 08:00:00" --end "2024-01-15 09:00:00" app.log

# Filter by log level
logslice --level ERROR app.log

# Filter by regex pattern
logslice --pattern "timeout|connection refused" app.log

# Combine filters with streaming from stdin
tail -f app.log | logslice --level WARN --pattern "database"

# Write output to a file
logslice --start "2024-01-15 08:00:00" --level ERROR app.log -o errors.log
```

### Options

| Flag | Description |
|------|-------------|
| `--start` | Start of time range (ISO format) |
| `--end` | End of time range (ISO format) |
| `--level` | Minimum log level (`DEBUG`, `INFO`, `WARN`, `ERROR`) |
| `--pattern` | Regex pattern to match against log lines |
| `--stream` | Enable streaming mode for live log tailing |
| `-o, --output` | Write results to a file instead of stdout |

---

## Requirements

- Python 3.8+

---

## License

This project is licensed under the [MIT License](LICENSE).
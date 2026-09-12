# lognest

Keep your log directories small without thinking about it

Built for my own use; public in case it helps someone.

## Install

```bash
pip install -r requirements.txt
python -m logwash --help
```

## Features

- Filter by age (--older-than) or size (--larger-than)
- Scan directories for log files by glob pattern
- Exit codes friendly for cron and CI
- Archive matched logs into a timestamped .tar.gz
- Dry-run mode shows what would happen, touches nothing

## Examples

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## Project structure

```text
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── bug_report.md
│   └── workflows/
│       └── ci.yml
├── docs/
│   ├── development.md
│   ├── faq.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   ├── cli.py
│   ├── errors.py
│   └── utils.py
├── tests/
│   └── test_cli.py
├── .editorconfig
├── .gitignore
├── CHANGELOG.md
├── SECURITY.md
├── pyproject.toml
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

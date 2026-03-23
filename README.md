# OpenAI Account Workflow & Credential Management Tool

A Python-based automation utility for account workflow handling and credential lifecycle management.

## Overview

This project is a Python utility for handling account-related workflows, including temporary email integration, verification-code retrieval, credential export, local backup, and inventory-style health checks.

It is designed for research, testing, and internal automation scenarios where structured credential handling and periodic validation are needed.

## Features

- Temporary email integration for verification-code retrieval
- Local token export and structured JSON backup
- Plain-text account archive output for internal management
- Optional inventory-style credential health checks
- Configurable polling intervals and threshold-based maintenance rules
- Proxy support for custom network routing

## Requirements

- Python 3.10+
- `curl_cffi`

Install dependency:

```bash
pip install curl_cffi
```

## Configuration

Open `wfxl_openai_regst.py` and edit the configuration section near the top of the file.

### Temporary Mail Settings

```python
MAIL_DOMAIN = "your-domain.com"
GPTMAIL_BASE = "https://your-domain.com"
ADMIN_AUTH = "xxxxx"
TOKEN_OUTPUT_DIR = os.getenv("TOKEN_OUTPUT_DIR", "").strip()
```

### Optional Inventory / Health-Check Settings

```python
ENABLE_CPA_MODE = True
CPA_API_URL = "https://your-domain.com:8317"
CPA_API_TOKEN = "xxxxxxx"
MIN_ACCOUNTS_THRESHOLD = 30
BATCH_REG_COUNT = 1
MIN_REMAINING_WEEKLY_PERCENT = 80
CHECK_INTERVAL_MINUTES = 60
```

## Usage

Run with default proxy:

```bash
python wfxl_openai_regst.py
```

Run with a custom proxy:

```bash
python wfxl_openai_regst.py --proxy http://127.0.0.1:7890
```

Run once and exit:

```bash
python wfxl_openai_regst.py --once
```

## Output

The script can generate:

- JSON credential files
- `accounts.txt` for local archival
- Optional upload-ready structured data for downstream internal systems

## Notes

- This repository is intended for research, testing, and internal workflow automation.
- Please ensure your usage complies with applicable laws, platform policies, and service terms.
- Review and adapt configuration values before running in any real environment.

## Author

- wenfxl

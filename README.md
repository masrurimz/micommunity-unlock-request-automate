# micommunity-unlock-request-automate

Automate the Xiaomi Mi Community bootloader unlock request at 00:00 Beijing time via ADB.

## How It Works

This script connects to your Xiaomi device via ADB, dumps the Mi Community app UI to find the "Apply for unlocking" button, then precisely clicks it at midnight Beijing time using NTP time synchronization.

## Requirements

- Python 3.10+
- [uv](https://docs.astral.sh/uv/) (recommended) or pip
- ADB installed and in PATH
- USB debugging enabled on your Xiaomi device
- Mi Community app open to the unlock request page

## Installation

```bash
# Clone the repo
git clone https://github.com/masrurimz/micommunity-unlock-request-automate.git
cd micommunity-unlock-request-automate

# Install with uv (recommended)
uv sync

# Or install with pip
pip install .
```

## Usage

### Live Mode (default)

Clicks "Apply for unlocking" at 23:59:59.800 Beijing time (GMT+8):

```bash
uv run mi-unlock
```

### Options

```
--clicks N       Number of clicks (default: 2)
--delay SECONDS  Delay between clicks (default: 2.0)
```

### Test Mode

Run at a custom time/timezone for testing:

```bash
uv run mi-unlock --test --test-timezone 5 --test-time 14:30
```

Test mode requires `--test-timezone` (UTC offset in hours) and `--test-time` (HH:MM or HH:MM:SS).

## How to Prepare Your Device

1. Enable Developer Options: **Settings → About Phone → Tap Build Number 7 times**
2. Enable USB Debugging: **Settings → Additional settings → Developer Options → USB Debugging**
3. Connect device via USB and authorize the ADB prompt
4. Open the Mi Community app and navigate to the unlock request page
5. Run the script — it will find the button and wait for the right time

## License

GPL-3.0-or-later — see [LICENSE](LICENSE) for details.

Original automation script by [chickendrop89](https://github.com/chickendrop89).

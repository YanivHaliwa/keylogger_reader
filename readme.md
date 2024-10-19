
# Keylogger reader

A Python-based keylogger for monitoring keystrokes and capturing the active window title on Linux systems. This tool uses `pynput` for listening to keystrokes and `xdotool` for tracking the active window.

## ⚠️ Disclaimer

**This tool is intended for educational purposes only. 
It is illegal to use a keylogger to monitor others without their explicit consent. 
Use this software responsibly and only on systems where you have permission. Misuse may lead to legal consequences.**

## Features

- **Keystroke Logging**: Captures and records all keystrokes.
- **Active Window Tracking**: Logs the title of the active window.
- **Modifier Key Support**: Accurately records combinations involving Shift, Ctrl, and Alt keys.
- **CapsLock Awareness**: Adjusts logging based on CapsLock state.
- **Multiple Output Formats**:
  - Formatted log with color-coding
  - Unformatted log
  - Text-only log

## Installation

### Prerequisites

- **Python 3.x**
- **`pynput` library** for keyboard listening:
  
  ```bash
  pip install pynput
  ```
- **`xdotool`** for active window detection:
  
  ```bash
  sudo apt-get install xdotool
  ```
- **`python-xlib`** for interacting with X11 on Linux:

  ```bash
  pip install python-xlib
  ```

### Clone the Repository

Clone the repository using the following command:

```bash
git clone https://github.com/YanivHaliwa/keylogger_reader.git
cd keylogger_reader
```

## Usage

### Run the Keylogger

To start the keylogger, run the following command:

```bash
python keylogger.py -l [--logfile] log.txt
```

- `--logfile` specifies the file where keystrokes will be logged. If not provided, the script will log to key_log.txt.

The script will create three log files:

- `[log_file].txt`:  Formatted with color coding, best viewed in ANSI-supported terminals or Sublime Text with an ANSI plugin.
- `[log_file]_not_formatted.txt`: Unformatted log without color coding, suitable for viewing in any text editor.
- `[log_file]_only_text.txt`: ontains only plain text-only keystrokes without any special keys and no color formatting.


To stop the keylogger, use `Ctrl+C`.

### Example Output


```ansi
\033[1;32mstart logging at 2024-10-19 15:17:09\033[0m

\033[1;34m[Mozilla Firefox]\033[0m - python\033[1;31m [ENTER] \033[0m

\033[1;34m[Sublime Text]\033[0m - well done\033[1;31m [ENTER] \033[0m

\033[1;32mstop logging at 2024-10-19 15:17:09\033[0m
```
 
- Window changes are logged as `[Window Title] - ` the first time you switch to a new window.
- Special keys are logged in square brackets, e.g., `[ENTER]`, `[ESC]`.
- Modifier key combinations are logged as `[CTRL+SHIFT+A]`.

## ⚠️ Security Note

After testing, make sure to delete any log files generated to prevent unintended data exposure, especially if the system is shared or used by multiple users.

## Note

This tool is for educational and research purposes only. Ensure you have proper authorization before using it in any environment.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your improvements.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

**Summary of the MIT License**: You are free to use, modify, and distribute this software as long as you include the original license. This software comes with no warranty.

## Tags

- `#keylogger`
- `#Python`
- `#Linux`
- `#pynput`
- `#xdotool`
- `#monitoring`
            
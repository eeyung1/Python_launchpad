# Tier 2 — Installing Python on Windows, macOS, and Linux

**Prepared by Emmanuel | Python Launchpad**

The goal is not just to install Python. We must also confirm that our computer can find it and execute instructions.

## Windows 10/11
1. Visit the official [Python downloads page](https://www.python.org/downloads/) and choose the current supported Python 3 release for Windows. Installation screens vary by release; follow the options shown by your installer.
2. If the installer offers **Add Python to PATH**, select it when appropriate. Newer Windows installation methods may manage commands differently.
3. Complete installation and open a **new** PowerShell window.
4. Check which command is available:

```powershell
python --version
py --version
```

If `python` does not work but `py` does, Python may still be installed correctly. On systems with the traditional Windows launcher, `py -0` lists detected installations, and `py -3.11 hello_python.py` selects Python 3.11 when installed. Availability depends on installation method.

**What is PATH?** PATH is an environment variable containing directories Windows searches for executable programs. These directories do not have to be nested or inside the current folder. If the Python executable's directory is missing, PowerShell may not recognize `python` even though Python is installed.

**Verify execution:**

```powershell
py -c "print('Hello, Python!')"
```

Or use `python -c "print('Hello, Python!')"` if `python` works.

If typing `python` opens a Store prompt or selects an unexpected executable, review Windows app execution aliases and your installation method.

## macOS
1. Download a supported macOS Python installer from [python.org](https://www.python.org/downloads/macos/) and complete installation. Alternatively, use a trusted package manager if already familiar with one.
2. Open Terminal and run:

```bash
python3 --version
python3 -c "print('Hello, Python!')"
```

3. If the command is not found, reopen Terminal and check that the installer completed and that its executable directory is available on PATH. Avoid replacing the operating system's managed Python installation.

## Ubuntu/Linux
Many Linux distributions already include Python 3. On Ubuntu, check first:

```bash
python3 --version
```

If unavailable, install using Ubuntu's package manager:

```bash
sudo apt update
sudo apt install python3 python3-venv python3-pip
```

Then verify:

```bash
python3 -c "print('Hello, Python!')"
```

Other Linux distributions use different package managers; follow their official instructions. Avoid removing or replacing system Python.

## Create and run a saved script
1. Make a folder called `python-launchpad` and open it in your editor or terminal.
2. Create `hello_python.py` and enter:

```python
print("Hello, Python!")
```

3. Save the file and open a terminal in the same directory.
4. Run `py hello_python.py` on Windows (if `py` is available), or `python hello_python.py` / `python3 hello_python.py` as appropriate.
5. Confirm the output is exactly `Hello, Python!`.

## Common checks
- `python --version` or `python3 --version` confirms the command resolves to an interpreter.
- `python -c "print('Hello, Python!')"` confirms it can execute code.
- Running the saved `.py` file confirms that you can find and execute your script.

For installation problems, see [Tier 4](tier-4-troubleshooting.md).

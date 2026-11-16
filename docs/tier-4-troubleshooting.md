# Tier 4 — Beginner-Friendly Troubleshooting

**Prepared by Emmanuel | Python Launchpad**

When something fails, read the error carefully. Identify the symptom, check the likely cause, and apply one solution at a time. The commands below are examples; use `python`, `python3`, or `py` according to your system.

## 1. `python` is not recognized (Windows)
**Symptom:** PowerShell says `python` is not recognized.

**Possible cause:** Python is not installed, or its executable directory is not in PATH.

**Try:** Run `py --version`. If that works, use `py` or configure your installation so `python` resolves correctly. Otherwise verify installation, follow the installer guidance for PATH, and reopen PowerShell. Confirm with `python --version` and a `print` test. Do not move Python into `C:\Windows`.

## 2. `ModuleNotFoundError`
**Symptom:** `ModuleNotFoundError: No module named 'requests'`.

**Possible cause:** The package is missing from the environment that runs the program, or a different interpreter is selected.

**Try:** Activate your project environment and run `python -m pip install requests`. Verify with `python -m pip show requests`. In an IDE, check its selected interpreter. If the missing module is a local file, also check its name and project layout.

## 3. `pip` is not recognized
**Symptom:** Terminal cannot find the `pip` command.

**Possible cause:** The pip command is not on PATH or pip is unavailable in the selected Python installation.

**Try:** `python -m pip --version` (or `python3 -m pip --version`). If missing, consult your Python distribution's installation guidance. Some installations support `python -m ensurepip --upgrade`; Ubuntu may require `sudo apt install python3-pip`. Prefer installing project packages in a virtual environment.

## 4. `PermissionError` or permission denied
**Symptom:** Installation or file writing fails with a permissions message.

**Possible cause:** The program is writing to a protected directory or packages are being installed globally.

**Try:** Work inside a folder you own, create and activate a virtual environment, and run `python -m pip install <package>` there. Check file permissions and file locks. Avoid using `sudo pip` as a routine fix.

## 5. `SyntaxError`
**Symptom:** Python highlights a line and reports invalid syntax.

**Possible cause:** Missing quotes, brackets, colons, or accidentally copying `>>>` into a script.

**Try:** Compare the code carefully with a working example:

```python
print("Hello, Python!")
```

Save and rerun. The `>>>` prompt belongs only to interactive mode.

## 6. Virtual environment activation fails on Windows
**Symptom:** PowerShell refuses to load `Activate.ps1`.

**Possible cause:** The activation path is wrong or the current execution policy blocks the script.

**Try:** Confirm `.venv` exists and that you're in the project folder. If your organization's policy permits it, use a process-scoped setting:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

Alternatively, skip activation and run the environment's interpreter directly: `.\.venv\Scripts\python.exe hello_python.py`. Do not weaken machine-wide security settings without understanding the consequences.

## 7. Python cannot find the script
**Symptom:** `can't open file ... [Errno 2] No such file or directory`.

**Possible cause:** You're in the wrong directory or the filename is different.

**Try:** Use `pwd` and `ls` on macOS/Linux or `Get-Location` and `Get-ChildItem` in PowerShell. Change into the folder containing the file, check its extension, then run it again.

## 8. Ubuntu reports an externally managed Python environment
**Symptom:** pip reports `externally-managed-environment` when installing packages globally.

**Possible cause:** The Linux distribution protects its system Python installation.

**Try:** Create and activate a virtual environment, then use `python -m pip install <package>` there. Do not bypass the protection just to install project dependencies.

## Final troubleshooting checklist
1. What exact command did I run?
2. What is the exact error message?
3. Which Python interpreter is active?
4. Am I in the correct folder?
5. Is the package installed in the same environment?
6. Can I run `print("Hello, Python!")` successfully?

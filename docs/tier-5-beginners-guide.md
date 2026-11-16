# Python Launchpad — Complete Beginner's Guide

**PY-SECTION 3 Mission Project: Set Up and Execute**  
**Technical writer and researcher:** Emmanuel  
**Squad leader and video producer:** John Ikwuobe

## Welcome

This guide is written for someone who has never programmed before. We will understand what Python is, install it, choose an environment, run our first program, manage project packages, and solve common errors. I will explain the ideas in straightforward language, because understanding *why* a command works is as important as copying it.

## Part 1 — Python and your first program

Python is a high-level programming language we use to write instructions for a computer. Its syntax is close to everyday English, making it easier for beginners to read, write, and understand. We can use Python for automation, websites, data analysis, artificial intelligence, and many other tasks.

I see a Python program as instructions we write in a `.py` file. The Python interpreter is the tool that executes those instructions. We do not have to write the instructions in binary ourselves.

## Why learn Python?
Python is beginner-friendly because it has readable syntax, a large collection of reusable packages, and a supportive learning community. It also lets us test ideas quickly instead of writing a lot of boilerplate code.

## What do I need to begin?
- A Windows, macOS, or Linux computer.
- A Python 3 installation.
- A terminal (PowerShell, Terminal, or a Linux shell).
- A code editor such as IDLE, VS Code, or PyCharm.
- Basic confidence with creating folders and saving files.

An internet connection helps with installation and packages, but a basic Python script can run offline once Python is installed.

## Two ways to run Python
**Interactive mode (REPL):** We can launch Python and enter instructions one at a time. It immediately shows the result, which is useful for calculations and experiments.

```text
>>> 2 + 3
5
```

The `>>>` symbol is the interactive prompt; **do not type it into a `.py` file**.

**Script mode:** We save instructions in a `.py` file and run the file whenever needed. This makes the program reusable, editable, and shareable.

Create `hello_python.py`:

```python
print("Hello, Python!")
```

Run it from the folder containing the file:

```bash
python hello_python.py
```

On many Linux/macOS systems use `python3 hello_python.py`; on Windows, `py hello_python.py` may also work. The expected output is:

```text
Hello, Python!
```

### Check your understanding
1. Explain Python in your own words.
2. What is the difference between an interpreter and a code editor?
3. Why is a saved `.py` file useful?

## Part 2 — Installing Python across operating systems


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

## Part 3 — Editors, virtual environments, and packages


| Tool | Good for | How to run a saved file |
|---|---|---|
| **IDLE** | A complete beginner who wants a simple Python shell and editor | File → New File, save `.py`, then Run → Run Module (F5) |
| **Visual Studio Code** | Someone working with Python, HTML, CSS, JavaScript, and other languages | Install the Python extension, select a Python interpreter, then use Run or the integrated terminal |
| **PyCharm** | Someone developing larger Python projects who wants integrated debugging and environment tools | Create/open a project, configure an interpreter, then run the file using the IDE's run action |

IDLE is commonly included in standard python.org installations but may be packaged separately on Linux. VS Code and PyCharm are separate downloads; install/configure a Python interpreter as needed.

## A first program in any editor
1. Create a folder for your project.
2. Open the folder or create a project in your chosen editor.
3. Create `hello_python.py`.
4. Enter `print("Hello, Python!")` and save.
5. Run the file using the editor's run action or the terminal.
6. Check that `Hello, Python!` appears.

## Virtual environments
A virtual environment is an isolated project environment that holds its own Python packages. If Project A needs Django 4.2 and Project B needs Django 5.2, separate environments prevent one project's packages from interfering with the other's.

From the project folder, create an environment:

```powershell
# Windows
py -m venv .venv
```

```bash
# macOS / Ubuntu
python3 -m venv .venv
```

Activate it:

```powershell
# Windows PowerShell
.\.venv\Scripts\Activate.ps1
```

```bash
# macOS / Ubuntu
source .venv/bin/activate
```

When activated, the prompt may show `(.venv)`. Then install a package:

```bash
python -m pip install requests
```

Deactivate with `deactivate`. This does **not** delete the environment or installed packages. Do not commit `.venv/` to Git.

## pip, PyPI, and requirements
A Python package is reusable code written to solve a task, so we do not have to build everything from the beginning. **PyPI** is a public package index; **pip** is the installer used to retrieve and install packages.

```bash
python -m pip --version
python -m pip install requests
python -m pip list
python -m pip freeze > requirements.txt
python -m pip install -r requirements.txt
```

Using `python -m pip` helps ensure packages go into the environment belonging to that Python interpreter. A `requirements.txt` records dependencies, but the project should also state which Python version it expects. For a simple Hello Python program, no third-party packages are needed.

## Quick practice
Create two separate project folders and virtual environments. Install a package in one, then confirm it is not automatically available in the other.

## Part 4 — What happens when Python runs?

### Source code, compilation, and the Python Virtual Machine

Python source code is the readable syntax we use to write instructions for a computer. Consider this example:

```python
print("Hello, Python!")
```

In **CPython**, the standard and most widely used Python implementation, source code is compiled into an intermediate form called **bytecode**. CPython's virtual machine then executes the bytecode through its runtime. This is a useful simplified model:

```text
Human-readable Python source (.py)
             |
             v
    CPython compilation
             |
             v
       Python bytecode
             |
             v
  CPython virtual machine
             |
             v
      Program execution
             |
             v
       Hello, Python!
```

Bytecode is **not** the same as the CPU's native machine instructions. The CPU ultimately runs machine instructions from the underlying Python runtime and other system components. We normally do not need to build a standalone executable file to run a Python script: we invoke the interpreter and give it the `.py` file.

CPython may save compiled bytecode for imported modules in `__pycache__/` as `.pyc` files. Directly running a standalone script does not normally produce a `.pyc` cache for that script just because it ran. Cached bytecode is a performance convenience, not the original source code.

### High-level and low-level languages

Python is a **high-level language** because its syntax is closer to human understanding than hardware instructions. We can write `print(10 + 20)` without manually controlling CPU registers. **Machine language** is made of instructions represented as binary values that a processor can execute. **Assembly language** expresses processor instructions in symbolic text. The fact that Python programs ultimately run on hardware does not make Python a low-level language.

### Python versus CPython

**Python** is the language and its defined behavior. **CPython** is one implementation of that language, written primarily in C. CPython includes the compiler, virtual machine, and runtime facilities used to execute programs. Other implementations include PyPy, Jython, and IronPython. We should distinguish the language from a specific implementation, just as we distinguish a recipe from one particular chef who prepares it.

### Implementation speed versus execution speed

**Implementation speed** is how quickly developers can write, test, and maintain a solution. Python often helps here through readable syntax, reusable libraries, rapid prototyping, and less boilerplate. **Execution speed** is how quickly the computer actually runs the program. For some CPU-heavy workloads, C or C++ programs can execute faster than equivalent pure-Python code, but actual performance depends on the workload, implementation, and libraries. Packages such as NumPy use optimized compiled code for many operations.

We should not choose a programming language only because a benchmark says it is faster. Development time, correctness, maintainability, deployment constraints, and the actual performance requirements all matter.

## Part 5 — Troubleshooting common problems


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

## Part 6 — Frequently asked questions

**Do I need an internet connection every time I run Python?**  
No. Once Python and any required packages are installed, a basic local program can run offline.

**Is VS Code the same as Python?**  
No. VS Code is an editor. Python is the language, and the interpreter executes the code.

**Why does `python` fail but `python3` work?**  
Command names vary by operating system and installation. Check which interpreter is installed and available on PATH.

**What does `>>>` mean?**  
It is the interactive Python prompt. Do not copy it into a `.py` script.

**Do I need a virtual environment for `print("Hello, Python!")`?**  
No. The Hello Python example uses no third-party packages. Virtual environments become especially useful when projects need their own dependencies.

**What is the difference between pip and PyPI?**  
PyPI hosts published packages; pip installs packages into a Python environment.

**Will `deactivate` delete my installed packages?**  
No. It only stops using that virtual environment in the current shell session.

**Does CPython translate every line directly into machine code?**  
No. CPython generally compiles source into bytecode, which its virtual machine executes.

**Why can't Python find my script?**  
Check the filename, extension, and directory from which you are running the command.

**Can I have more than one Python version installed?**  
Yes. On supported Windows setups, the `py` launcher can select a version. On other systems, interpreters and environments can be selected using their respective commands and paths.

## Part 7 — Final practice exercise

1. Verify your Python installation using a version command.
2. Open IDLE, VS Code, or PyCharm.
3. Create `hello_python.py` and save `print("Hello, Python!")`.
4. Run the script and confirm the message appears.
5. Explain the difference between the editor and interpreter.
6. Create a `.venv` environment, activate it, and deactivate it.
7. Explain why a project may need `requirements.txt`.
8. Describe how source code becomes bytecode and is executed by CPython.

## Final submission and further reading

The written guide is one of the mission's two final deliverables. The other is a **5–10-minute screen-capture video** showing a real Python installation on one operating system, an editor, creation and execution of a script, visible `Hello, Python!` output, and narration. See `video/video-script.md` for the recording outline and `video/video-link.md` for the eventual link. The video must be recorded and verified before the mission is considered complete.

For technical references and official documentation, see `docs/references.md`. This guide is self-contained: readers can follow the instructions without needing to open the tier-specific files.

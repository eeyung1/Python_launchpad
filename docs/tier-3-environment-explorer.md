# Tier 3 — Exploring Python Development Environments

**Prepared by Emmanuel | Python Launchpad**

Python is the language, and its interpreter executes programs. An editor or IDE is the workspace where we write, organize, debug, and manage our code. The editor itself is not the interpreter.

## Choosing a tool
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

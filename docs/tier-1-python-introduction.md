# Tier 1 — Introduction to Python

**Prepared by Emmanuel | Python Launchpad**

## What is Python?
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

## Beginner check
1. Explain Python in your own words.
2. What is the difference between an interpreter and a code editor?
3. Why is a saved `.py` file useful?

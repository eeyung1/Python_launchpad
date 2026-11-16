# Video Recording Script — Python Launchpad

**Draft for John (video producer), with technical content prepared by Emmanuel**  
**Target length:** 5–10 minutes  
**Platform for demonstration:** Choose one actual operating system and use its real commands. Do not claim to demonstrate an installation that was not recorded.

## 0:00–0:45 — Introduction
"Welcome to Python Launchpad. Python is a programming language we use to write instructions in readable syntax. Today I will show how to install it, check it works, choose an editor, and run a first program."

**On screen:** Title, operating system name, official Python download page.

## 0:45–3:00 — Installation
**On screen:** Download the official Python 3 installer (or use the official package manager instructions on Linux); show the installation steps. On Windows, explain PATH and the installer's current command options. Avoid skipping the installation step in the final recording.

**Narration:** "PATH is a list of folders the computer searches when we type a program name. We need to know how our system finds Python."

## 3:00–4:00 — Verify Python
**On screen:** Open a fresh terminal and run the appropriate version command: `py --version` or `python --version` (Windows), or `python3 --version` (macOS/Linux). Then run a one-line print command.

**Narration:** "Checking the version confirms the command is available. Printing a message confirms Python can execute instructions."

## 4:00–5:30 — Editor and file
**On screen:** Open IDLE, VS Code, or PyCharm; create `hello_python.py`; type and save:

```python
print("Hello, Python!")
```

**Narration:** "The editor helps me write the program, but the Python interpreter executes it. Saving the instructions in a `.py` file means I can run them again."

## 5:30–7:00 — Run the script
**On screen:** Show the file and terminal together if possible. Run `py hello_python.py` or `python3 hello_python.py` depending on OS. **Keep `Hello, Python!` clearly visible.**

**Narration:** "We have created and executed our first Python script. The `print` instruction displays the message on the screen."

## 7:00–8:30 — Troubleshooting and wrap-up
**On screen:** Point out where to check PATH, filename, current folder, and Python version. Mention virtual environments for later projects.

**Narration:** "If Python is not recognized, check the installation and PATH. If a script cannot be found, check your current folder and filename. For projects with packages, virtual environments help us keep dependencies separate."

## Recording quality checklist
- [ ] Installation visibly demonstrated on one OS.
- [ ] Editor visibly shown.
- [ ] File creation and save visibly shown.
- [ ] Script execution visibly shown.
- [ ] `Hello, Python!` output readable.
- [ ] Narration audible and clear.
- [ ] Duration between 5 and 10 minutes.
- [ ] Final recording uploaded and accessible; link entered in `video/video-link.md` by the video producer.

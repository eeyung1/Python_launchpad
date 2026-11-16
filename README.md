# Python Launchpad — Set Up and Execute

**PY-SECTION 3 Mission Project** · Squad of two: **John Ikwuobe** (squad leader and video producer) and **Emmanuel Eyung** (technical writer and research specialist).

Welcome to Python Launchpad! This project helps complete beginners install Python, choose an editor, run their first script, understand environments and package management, and troubleshoot common problems.

## Start here

1. Read the **[complete Beginner's Guide](docs/tier-5-beginners-guide.md)**. This is the standalone written deliverable for Tier 5.
2. Follow the instructions for your operating system in the [cross-platform setup guide](docs/tier-2-cross-platform-setup.md).
3. Run the sample script:

   ```bash
   python3 scripts/hello_python.py
   ```

   On Windows, use `py scripts/hello_python.py` when the Python Launcher is available. Expected output:

   ```text
   Hello, Python!
   ```

4. Review the [troubleshooting desk](docs/tier-4-troubleshooting.md) if you encounter an error.

## Documentation by tier

| Tier | Document | Coverage |
| --- | --- | --- |
| 1 | [Python Introduction](docs/tier-1-python-introduction.md) | What Python is, why it matters, and your first program |
| 2 | [Cross-Platform Setup](docs/tier-2-cross-platform-setup.md) | Windows, macOS, and Linux installation and verification |
| 3 | [Environment Explorer](docs/tier-3-environment-explorer.md) | IDLE, VS Code, PyCharm, virtual environments, pip and PyPI |
| 4 | [Troubleshooting Desk](docs/tier-4-troubleshooting.md) | Eight common errors, causes, and practical solutions |
| 5 | [Complete Beginner's Guide](docs/tier-5-beginners-guide.md) | All above plus interpreter architecture, CPython, bytecode, language levels, and performance |

Other resources: [research references](docs/references.md), [Hello Python script](scripts/hello_python.py), [Emmanuel's handoff notes](EMMANUEL-HANDOFF.md), and [screenshot guidance](screenshots/README.md).

## Two final mission outputs

- [x] **Written beginner's guide** — prepared for review and integration.
- [x] **Video script** — [recording outline](video/video-script.md) drafted for John.
- [ ] **5–10-minute screen-capture video** — must demonstrate a real installation on one OS, an editor, creation and execution of a `.py` file, visible `Hello, Python!` output, and clear narration.
- [ ] **Video upload and link verification** — record the URL and access details in [video-link.md](video/video-link.md).
- [ ] **Final QA and classroom submission** — check platform-specific instructions, file accessibility, audio/visual quality, and the deadline.

The example requires Python 3 and **no external packages**; [`requirements.txt`](requirements.txt) documents that fact. For projects using packages, make a virtual environment before installing dependencies.

## Collaboration

Contributions should be developed on feature branches, verified, and reviewed in pull requests before merging to `main`. Preserve each squad member's files and contributions. Do not claim the video or final submission is complete until the recording and access checks have actually been performed.

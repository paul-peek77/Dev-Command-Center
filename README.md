Dev Command Center (DCC)
A portable, cross‑platform developer cockpit for project analysis, purification, and deterministic reconstruction. Provided for portfolio review only. Redistribution or reuse is not permitted.
https://img.shields.io/badge/platform-Debian%20%7C%20Windows-blue https://img.shields.io/badge/languages-Node.js%20%7C%20Python-green https://img.shields.io/badge/status-Stable-brightgreen https://img.shields.io/badge/license-Proprietary-red
Overview
The Dev Command Center (DCC) is a unified toolkit designed to operate consistently across Debian/Linux and Windows environments. It provides a structured set of utilities for inspecting, documenting, cleaning, and restoring project directories using a hybrid Node.js + Python architecture.
The system is fully self‑contained, dependency‑free, and portable across filesystems — including exFAT, USB drives, and dual‑boot environments.
DCC is built as a developer cockpit: a foundation for expanding into broader workflows such as project scaffolding, environment validation, cleanup utilities, and AI‑assisted ingestion.
Key Features
Feature	Description
Cross‑Platform Execution	Automatically detects OS and routes to the correct toolchain.
Directory Tree Generator	Produces a clean ASCII tree of any project directory.
Manifest Generator	Creates a deterministic, sorted file manifest.
Purification Tools	Normalizes paths and corrects formatting issues.
Restoration Tools	Reconstructs text‑based projects from manifests.
Portable Architecture	Runs from any directory, partition, or USB drive.
Modular Design	Easy to extend with new tools and workflows.
Project Structure
Code
Dev-Command-Center/
├─ src/
│  ├─ ui/
│  │  └─ menu.js          # Text-based menu (TUI)
│  ├─ core/
│  │  └─ router.js        # Routes menu choices to tools
│  └─ tools/
│     ├─ devtree.js       # Node wrapper: directory tree generator
│     ├─ manifest.js      # Node-only: file manifest generator
│     ├─ purifier.js      # Node wrapper: calls purify-es-*.py
│     ├─ restorer.js      # Node wrapper: calls restore-es-*.py
│     ├─ gen-es-deb.py    # Python: Debian-specific generator
│     ├─ gen-es-win.py    # Python: Windows-specific generator
│     ├─ purify-es-deb.py # Python: Debian-specific purifier
│     ├─ purify-es-win.py # Python: Windows-specific purifier
│     ├─ restore-es-deb.py# Python: Debian-specific restorer
│     └─ restore-es-win.py# Python: Windows-specific restorer
├─ bin/
│  └─ dcc                 # Launcher script
├─ package.json
└─ README.md
Installation & First Run
Debian/Linux
bash
chmod +x bin/dcc
node bin/dcc
Optional PATH addition:
bash
export PATH="$PWD/bin:$PATH"
dcc
To make it permanent:
bash
echo 'export PATH="/path/to/Dev-Command-Center/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
Windows
Ensure Node and Python are installed and on PATH.
Run with:
bat
node bin\dcc
Optional dcc.cmd wrapper:
bat
@echo off
node "%~dp0..\src\ui\menu.js" %*
Add the bin directory to your PATH and run:
bat
dcc
Usage
Navigate to any project directory you want to operate on:
bash
cd /path/to/project
dcc
Menu:
Code
=== DEV COMMAND CENTER ===

1. Generate Dev Tree
2. Generate Manifest
3. Run Purifier
4. Run Restorer
5. Exit
All output files are written to the current working directory.
Tools
1. Directory Tree Generator
Output: devtree-output.txt Generates a clean ASCII directory tree, ignoring noise such as .git, node_modules, and __pycache__.
2. Manifest Generator
Output: manifest-output.txt Creates a deterministic, sorted list of all files in the project.
3. Purifier
Output: purifier-log.txt Runs the OS‑specific purifier:
    • Debian: purify-es-deb.py
    • Windows: purify-es-win.py
Normalizes paths, corrects formatting issues, and prepares manifests for restoration.
4. Restorer
Output: restorer-log.txt Runs the OS‑specific restorer:
    • Debian: restore-es-deb.py
    • Windows: restore-es-win.py
Reconstructs text‑based projects from manifests.
Why This Project Matters
The Dev Command Center demonstrates:
    • cross‑platform engineering
    • hybrid architecture design
    • deterministic workflows
    • filesystem traversal
    • reversible transformations
    • tool orchestration
    • clean, modular code organization
    • practical problem‑solving across OS boundaries
This project showcases your ability to design systems that are portable, predictable, and extensible — a key skill for systems engineering, DevOps, and platform roles.
Tech Stack
    • Node.js — orchestration, routing, UI
    • Python — platform‑specific engines
    • Filesystem APIs — traversal, indexing, reconstruction
    • Cross‑platform execution — OS detection + tool routing
Future Expansion
    • project scaffolding tools
    • dependency mapping
    • codebase introspection
    • environment validation
    • cleanup utilities
    • AI‑assisted ingestion workflows
    • plugin system for custom tools
    • multi‑project batch operations
    • remote execution support
Security & Privacy
The Dev Command Center:
    • does not transmit data
    • does not collect analytics
    • does not communicate with external services
    • operates entirely on the local machine
License
Provided for portfolio review only. Redistribution or reuse is not permitted.

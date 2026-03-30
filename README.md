# oss-audit-24BCE10425

> A capstone project for the Open Source Software course, involving a detailed audit of the Apache HTTP Server, supported by Linux-based shell scripting assignments.

---

## Student Information

| Field                  | Details              |
|------------------------|----------------------|
| **Student Name**       | MOLLY PAREEK      |
| **Registration Number**| 24BCE10425         |
| **Course**             | Open Source Software |

---

## Project Overview

This project presents a comprehensive audit of the **Apache HTTP Server**, one of the most widely deployed open-source web servers in the world. The audit covers:

- The origin, history, and evolution of Apache HTTP Server
- Its licensing model (Apache License 2.0) and implications
- The surrounding open-source ecosystem and community
- A comparison with proprietary web server alternatives
- Practical implementation through five Linux-based Bash shell scripts that demonstrate core open-source system administration concepts

The scripting component reinforces theoretical understanding by applying Linux command-line tools, file handling, process inspection, and system auditing techniques in a real environment.

---

## Tech Stack

| Component            | Details                                                          |
|----------------------|------------------------------------------------------------------|
| **Operating System** | Kali Linux / Ubuntu (Linux-based)                                |
| **Shell**            | Bash (`/bin/bash`)                                               |
| **Web Server**       | Apache HTTP Server (`apache2`)                                   |
| **Package Manager**  | `apt` (Advanced Package Tool)                                    |
| **Core Utilities**   | `uname`, `whoami`, `dpkg`, `du`, `grep`, `awk`, `date`, `uptime` |

---

## Project Structure

```
open-source-audit-apache/
│
├── script1.sh          # System Identity Report
├── script2.sh          # FOSS Package Inspector
├── script3.sh          # Disk and Permission Auditor
├── script4.sh          # Log File Analyzer
├── script5.sh          # Open Source Manifesto Generator
│
└── README.md           # Project documentation
```

---

## Setup Instructions

### Prerequisites

Ensure you are running a Debian/Ubuntu-based Linux distribution (Kali Linux or Ubuntu recommended).

### Step 1 — Update Package Lists

```bash
sudo apt update
```

### Step 2 — Install Apache HTTP Server

```bash
sudo apt install apache2 -y
```

### Step 3 — Verify Installation

```bash
apache2 -v
```

### Step 4 — Make Scripts Executable

```bash
chmod +x script1.sh script2.sh script3.sh script4.sh script5.sh
```

---

## How to Run the Scripts

| Script       | Command                                        |
|--------------|------------------------------------------------|
| `script1.sh` | `./script1.sh`                                 |
| `script2.sh` | `./script2.sh`                                 |
| `script3.sh` | `./script3.sh`                                 |
| `script4.sh` | `./script4.sh /var/log/apache2/error.log error`|
| `script5.sh` | `./script5.sh`                                 |

> **Note:** `script4.sh` requires two arguments — the path to a log file and a keyword to search for. The keyword defaults to `error` if not provided.

---

## Script Descriptions

| Script       | Title                        | Description                                                                                                  |
|--------------|------------------------------|--------------------------------------------------------------------------------------------------------------|
| `script1.sh` | System Identity Report       | Displays key system information including kernel version, logged-in user, distro name, uptime, and date/time. |
| `script2.sh` | FOSS Package Inspector       | Checks whether `apache2` is installed using `dpkg`, displays package details, and uses a `case` statement to print a philosophy note about the package. |
| `script3.sh` | Disk and Permission Auditor  | Iterates over a predefined list of system directories, reporting their permissions, ownership, and disk usage. Also checks for the Apache configuration directory. |
| `script4.sh` | Log File Analyzer            | Accepts a log file path and keyword as arguments, counts keyword occurrences line by line using a `while` loop, and displays the last five matching lines. |
| `script5.sh` | Open Source Manifesto Generator | Prompts the user for three inputs, collects system metadata, and generates a personalized open-source manifesto saved to a `.txt` file. |

---

## Output Explanation

- **script1.sh** — Prints a formatted system audit panel with distribution, kernel, user, home directory, uptime, date, and GPL license note.
- **script2.sh** — Confirms whether Apache is installed and outputs version/package details. The `case` block prints a contextual philosophy note.
- **script3.sh** — Produces a directory audit table showing permissions, owner, group, and size for `/etc`, `/var/log`, `/home`, `/usr/bin`, `/tmp`, and the Apache config directory.
- **script4.sh** — Outputs a log analysis report: file name, keyword searched, total occurrence count, and the last five matching log lines.
- **script5.sh** — Generates a `manifesto_<username>.txt` file containing a personalised open-source manifesto based on user-provided inputs, then displays it on screen.

---

## Concepts Used

The following shell scripting and Linux concepts are demonstrated across the five scripts:

- **Variables** — User-defined and system-derived (e.g., `$(whoami)`, `$(uname -r)`)
- **User Input** — `read -p` for interactive prompts
- **Conditional Statements** — `if-else` for file existence and package checks
- **Case Statements** — Multi-branch logic based on package names
- **Loops** — `for` loop over arrays; `while` loop over file lines
- **Command-line Arguments** — Positional parameters `$1`, `$2` with defaults
- **File I/O** — Reading files with `IFS= read -r`, writing output with `>`
- **Text Processing** — `grep`, `awk`, `cut`, `tail`, `tr`
- **System Commands** — `du`, `ls -ld`, `dpkg`, `date`, `uptime`, `uname`
- **Exit Codes** — `exit 1` for error handling and early termination
- **Retry Logic** — Re-checking conditions after a `sleep` delay

---

## Notes

- All scripts are written for **Linux environments only**. They will not run natively on Windows or macOS without a compatibility layer.
- Scripts must be granted execute permission before running (`chmod +x <script>`).
- `script4.sh` requires a valid, readable log file as its first argument. An appropriate test file is `/var/log/syslog` on Ubuntu or `/var/log/kern.log` on Kali Linux.
- `script3.sh` reads system directories that may require elevated permissions for accurate size reporting. Run with `sudo` if size values appear incomplete.
- The manifesto file generated by `script5.sh` is saved in the current working directory as `manifesto_<username>.txt`.

---

## Conclusion

This project demonstrates a practical understanding of open-source principles through the lens of the Apache HTTP Server — a cornerstone of the open web. The scripting assignments reinforce foundational Linux administration skills and reflect the values central to open-source culture: transparency, collaboration, and freedom to inspect and modify software. Together, the theoretical audit and practical scripts form a complete study of open-source software in a real-world context.

---

*Submitted as part of the Open Source Software course assignment.*

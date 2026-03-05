# Sentinel 🛡️ – Personal Session Guard (Python)

Sentinel is a small security tool that helps you monitor **who is using your own computer**.

The first version focuses on a simple scenario:  
if someone uses your machine and they are **not you**, Sentinel will:

- capture a picture of the person using the device (via webcam),
- record a summary of the session activity (e.g., active windows, timestamps),
- send you an email notification with the captured evidence.

The goal of this project is educational and defensive:  
to protect your **own devices** in case of theft or unauthorized access, **not** to spy on others.

---

## Features (v1 – in progress)

- 🔍 Basic “non-owner” session detection.
- 📸 Webcam capture of the current user.
- 📝 Local session logging (what happens during the suspicious session).
- 📧 Email notification with attached picture and log file.

---

## Future Ideas

- Per-OS integrations (Windows / macOS / Linux) with dedicated system APIs.
- Encrypted storage of evidence.
- Web dashboard to browse past security events.
- Multi-device support.

---

## Tech Stack

- Language: **Python 3**
- OS-specific modules: separate implementations for **Windows** and **macOS**
- Notifications: **SMTP email** (configurable)

**Legal & ethical note:**  
Use Sentinel **only on devices that you own or administer** and always respect local laws and privacy rules.

# Project - tree
sentinel/ <br>
├─ README.md # Sentinel 🛡️ – Personal Session Guard (Python) <br>
│ # Sentinel helps you monitor who is using your own computer.
│ # v1 focuses on detecting a non-owner session, capturing a picture, <
│ # logging session activity, and sending an email notification.
│ # Goal: Educational & defensive, not intended for spying.
│
├─ LICENSE # Legal license for open-source usage (optional but recommended)
├─ .gitignore # Ignore build artifacts, env, logs, etc.
├─ requirements.txt # Python dependencies (OpenCV, emails, OS libs, etc.)
├─ .env.example # Example mail config (SMTP settings, sender, etc.)
│
├─ sentinel/ # Main Python package
│ ├─ init.py
│ ├─ config.py # Loads configuration (email settings, owner identity, paths, etc.)
│ │
│ ├─ core/ # Cross-platform logic (OS-independent)
│ │ ├─ init.py
│ │ ├─ detector.py # Basic "non-owner" session detection
│ │ ├─ session_logger.py # Records what happens during the session (active windows, timestamps)
│ │ ├─ notifier.py # Sends email notifications with evidence attached
│ │ └─ models.py # Simple data models (SessionInfo, Evidence, Event)
│ │
│ ├─ os_windows/ # Windows-specific implementation
│ │ ├─ init.py
│ │ ├─ system_api.py # Webcam capture, current user, foreground window, etc.
│ │ └─ service.py # Auto-start integration (Task Scheduler / Service)
│ │
│ ├─ os_macos/ # macOS-specific implementation
│ │ ├─ init.py
│ │ ├─ system_api.py # Webcam capture, current user, window title, etc.
│ │ └─ service.py # Auto-start integration via launchd
│ │
│ └─ cli/
│ ├─ init.py
│ └─ main.py # Entry point: launches detection + notification logic
│
├─ docs/ # Documentation for contributors and users
│ ├─ architecture.md # Description of core architecture + OS separation
│ ├─ setup_windows.md # How to install and run Sentinel on Windows
│ └─ setup_macos.md # How to install and run Sentinel on macOS
│
└─ tests/ # Unit tests (for core components only)
├─ init.py
├─ test_detector.py # Tests for "non-owner" session detection logic
└─ test_notifier.py # Tests email notification behavior




# Sentinel 🛡️ – Personal Session Guard (Python)

Sentinel is a lightweight **personal security tool** that helps you monitor **who is using your computer**.

If someone accesses your machine and they are **not the authorized owner**, Sentinel can:

- 📸 capture a picture using the webcam
- 📝 log the activity of the suspicious session (active windows, timestamps)
- 📧 send an email notification with the captured evidence

The goal of this project is **educational and defensive**:  
Sentinel is designed to protect **your own devices in case of theft or unauthorized access**, not to spy on others.

---

# Features (v1 – In Progress)

- 🔍 Basic **non-owner session detection**
- 📸 **Webcam capture** of the current user
- 📝 **Session logging** (window activity + timestamps)
- 📧 **Email notifications** with attached evidence

---

# Future Ideas

Possible improvements for future versions:

- Full OS integrations (**Windows / macOS**)
- Encrypted storage of captured evidence
- Web dashboard to browse past security events
- Multi-device monitoring
- Mobile notification support

---

# Tech Stack

Language  
- Python 3

Libraries  
- OpenCV
- SMTP (email notifications)

Architecture  
- Cross-platform core logic
- OS-specific modules for Windows and macOS

---

# Run Sentinel

### 1. Install dependencies

```bash
pip install -r requirements.txt
```
### 2. Configure email settings
Create a .env file based on: .env.local

### 3.Run the program
```bash
python -m sentinel.cli.main
```

---
# Project Structure
```text
sentinel/
│
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
├── .env.example
│
├── sentinel/                 # Main Python package
│   ├── __init__.py
│   ├── config.py
│   │
│   ├── core/                 # Cross-platform logic
│   │   ├── __init__.py
│   │   ├── detector.py
│   │   ├── session_logger.py
│   │   ├── notifier.py
│   │   └── models.py
│   │
│   ├── os_windows/           # Windows-specific implementation
│   │   ├── __init__.py
│   │   ├── system_api.py
│   │   └── service.py
│   │
│   ├── os_macos/             # macOS-specific implementation
│   │   ├── __init__.py
│   │   ├── system_api.py
│   │   └── service.py
│   │
│   └── cli/
│       ├── __init__.py
│       └── main.py
│
├── docs/
│   ├── architecture.md
│   ├── setup_windows.md
│   └── setup_macos.md
│
└── tests/
    ├── __init__.py
    ├── test_detector.py
    └── test_notifier.py
```
---
# Security & Ethics
Sentinel must only be used on devices that you own or administer.

Always respect:

- local laws

- privacy regulations

- ethical use of monitoring software

This project is intended for personal security and learning purposes only.

---
---

# Project Status

🚧 **This project is currently under active development.**

Sentinel is still evolving and new features are being implemented.  
The current version focuses on the **core detection and notification system**.

Planned improvements include:

- Improved non-owner detection algorithms
- Stronger security for stored evidence

Contributions, feedback, and suggestions are welcome.


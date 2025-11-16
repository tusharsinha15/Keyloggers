
## 🔑 Python Keylogger Proof-of-Concept for Security Education

This repository provides simple Python scripts designed to demonstrate the fundamental functionality of a **keylogger**. The primary goal is to serve as an **educational resource** for security enthusiasts, students, and developers to understand the mechanics of keystroke capture, which is essential knowledge for building effective defensive security measures.

---

### ⚠️ Ethical Disclaimer: Read Before Proceeding

**This tool is strictly intended for ethical security research and educational use only.**

* **Unauthorized or malicious use of this software is strictly forbidden and illegal.**
* Users must ensure they are only running these scripts on systems they own or have **explicit, authorized permission** to monitor.
* The project author assumes no responsibility for any misuse or illegal activities resulting from the use of this software.

---

### Key Functionality

This project contains two distinct scripts, both leveraging the `pynput` library for keyboard event handling:

#### 1. Basic Local Logging (`Keyloggers.py` Analysis)

This script focuses on local capture and storage of user input:

* It monitors and records all key presses, including standard alphanumeric characters and special keys (e.g., `Key.caps_lock`, `Key.shift`).
* The captured keystrokes are written to a local file (`log.txt`).
* It includes a built-in release condition to stop the listener when the $\text{ESC}$ key is pressed.
* A sample output demonstrating the format of the captured data is included in the repository (`log (1).txt`).

#### 2. Email Exfiltration Proof-of-Concept (PoC) (`Keylogger.py` Analysis)

This script demonstrates a method of **remote data exfiltration**, often used by attackers to steal credentials or sensitive information:

* It efficiently handles special keys, converting `Key.space` to a space, `Key.enter` to a newline character, and `Key.backspace` to a `<` symbol for cleaner output.
* It accumulates keystrokes in a buffer until a specified threshold (e.g., 100 characters) is reached.
* Upon reaching the threshold, the script uses the `smtplib` library to package and send the collected keystrokes as an email to a predefined recipient.

---

### Prerequisites and Setup

To run these scripts, you will need the following dependencies:

* **Python 3.x**
* **`pynput` library**

#### Email Configuration

The PoC script (`Keylogger.py`) uses hardcoded email settings for demonstration. To successfully test the email exfiltration feature, users must configure these variables with their own credentials. Note that if using providers like Gmail, you may need to generate and use a specific **App Password** instead of your primary account password for security reasons.

---

### Project Goal

This project aims to increase awareness about keyboard monitoring techniques, encouraging a focus on defensive programming and robust system security to mitigate such vulnerabilities.

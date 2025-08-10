# 🛡️ Wazuh Security Monitoring – PoC Collection

This repository contains my **Proof of Concepts (PoCs)** demonstrating different Wazuh capabilities tested on **Kali Linux**.  
Each PoC is documented in its own Markdown file with configuration steps, commands, and screenshots.

## 📂 Included PoCs
- **File Integrity Monitoring (FIM)** – Detects file creation, modification, and deletion in monitored directories.
- **Command Monitoring** – Detects when Netcat is running in listening mode.
- **Vulnerability Detection** – Identifies unpatched CVEs in the operating system and installed applications.

## 📖 How to Use
1. Open any `.md` file in this repo to view the step-by-step PoC.
2. Follow the documented configurations on your own Wazuh setup.
3. Use the provided screenshots in the `assets/` folder for reference.

## 💻 Tested Environment
- **Endpoint:** Kali Linux (latest)
- **Wazuh Server:** Configured for FIM, command monitoring, and vulnerability detection
- **Tools Used:** Wazuh Agent, Netcat, OS utilities

---

📌 *These PoCs are for educational and lab testing purposes only.*

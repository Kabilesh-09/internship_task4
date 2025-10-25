# Task 4 - Firewall Configuration (Windows)

## 🔰 Objective
To configure and test basic firewall rules to allow or block network traffic using Windows Firewall.

---

## 🧩 Steps Performed
1. Opened Command Prompt as Administrator.
2. Listed all existing firewall rules.
3. Added rule to block inbound TCP traffic on port **23 (Telnet)**.
4. Verified the rule was active.
5. Tested Telnet connection — it failed (blocked as expected).
6. Deleted the test rule to restore the firewall’s original state.

---

## ⚙️ Commands Used
```bash
netsh advfirewall firewall show rule name=all
netsh advfirewall firewall add rule name="Block Telnet Port 23" dir=in action=block protocol=TCP localport=23
netsh advfirewall firewall show rule name="Block Telnet Port 23"
telnet 127.0.0.1 23
netsh advfirewall firewall delete rule name="Block Telnet Port 23"


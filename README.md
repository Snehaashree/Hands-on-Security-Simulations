# 🛡️ Cybersecurity Workshop Report

**Trainer:** Mr. Radhe Shyam – Cybersecurity Expert  
**Duration:** 2 Days  
**Mode:** Hands-on Practical Sessions  

---

## 🧠 Overview
This workshop focused on developing **practical cybersecurity skills** through real-world attack and defense simulations.  
We deployed vulnerable applications, simulated phishing attacks, and explored online anonymity tools.

---

## ⚙️ Tools & Technologies Used
- 🖥️ **Quick Emulator (QEMU)** – Virtual machine deployment  
- 🧃 **OWASP Juice Shop** – Web application vulnerability testing  
- ✉️ **GoPhish** – Phishing simulation and awareness  
- 🕵️‍♂️ **Tor Browser** – Anonymity and secure browsing  

---
## 🧰 Setup & Installation (Quick)

**Quick steps to reproduce the lab environment:**

- **Run Juice Shop (Docker, quickest):**
docker run --rm -p 8080:3000 bkimminich/juice-shop
# then open http://localhost:8080
Start GoPhish (if installed on Kali):
cd gophish
./gophish
# open https://localhost:3333 (credentials shown in terminal)
Launch Tor Browser:
torbrowser-launcher

## 🔍 Day 1: Web Vulnerabilities (OWASP Juice Shop)
- Deployed **OWASP Juice Shop** on a virtual machine using **Quick Emulator (QEMU)**.  
- Accessed the vulnerable web app via **port 8080** in the browser.  
- Explored and exploited **OWASP Top 10 vulnerabilities**, including:
  - Cross-Site Scripting (XSS)
  - SQL Injection
  - Broken Authentication
  - Insecure Direct Object References (IDOR)
- Learned how insecure coding practices can lead to critical security flaws.  

### 📸 Screenshot
![OWASP Juice Shop](images/juice-shop.png)  
*OWASP Juice Shop web interface hosted locally on port 8080.*

---

## ✉️ Day 2: Phishing Simulation (GoPhish)
- Used **GoPhish** to simulate real-world phishing campaigns.  
- Designed and sent **phishing emails** with custom landing pages.  
- Tracked **open, click, and credential capture** statistics in the GoPhish dashboard.  
- Learned attacker perspectives and the importance of **security awareness training**.  

### 📸 Screenshot
![GoPhish Dashboard](images/gophish-dashboard.png)  
*GoPhish campaign tracking showing email delivery and click statistics.*

---

## 🕵️‍♂️ Session 3: Online Anonymity (Tor Browser)
- Used **Tor Browser** to understand how **onion routing** protects privacy.  
- Observed the **network hops (relays)** between user and destination.  
- Discussed **VPNs, encryption**, and **digital footprint reduction** techniques.  

### 📸 Screenshot
![Tor Browser Circuit](images/tor-browser.png)  
*Tor Browser showing anonymous routing hops.*

---

## 🗣️ Reflection & Q&A
At the end of each session, we had a **reflection and Q&A round** where the trainer asked both technical and non-technical questions related to the previous activities.  
This helped us **revisit key concepts**, share insights, and strengthen our **communication and analytical thinking**.

---

## 🎯 Key Learnings
- Understood practical web exploitation techniques and their mitigations.  
- Learned how phishing attacks are planned, executed, and analyzed.  
- Gained awareness of anonymity, encryption, and safe browsing practices.  
- Strengthened both **offensive (red team)** and **defensive (blue team)** cybersecurity perspectives.
- 
## Independent setup notes:
Independently from the instructor’s QEMU workflow, I also explored alternate deployments during the lab. I configured the built-in GoPhish instance available on Kali and launched a quick phishing test in two simple steps. I additionally cloned the OWASP Juice Shop repository and ran the application on my Kali VM using Docker (git clone ... + docker run), to verify that the target works on the VM environment as well. This independent practice helped me validate multiple deployment methods and solidify my hands-on experience.
---

## 🏁 Outcome
This workshop enhanced my **hands-on cybersecurity experience**, deepened my understanding of **ethical hacking**, and provided exposure to real-world **cyber defense strategies**.

---

## 💻 Repository Info
This repository documents my learnings and practical exercises from the **2-day Cybersecurity Workshop** conducted by **Mr. Radhe Shyam**.

Feel free to explore, fork, and connect if you’re interested in similar cybersecurity practices. 🧩  

📬 **Author:** [Snehashree N](https://github.com/Snehaashree)    
🔒 **Focus Areas:** Web Security | Phishing | Anonymity | Ethical Hacking  

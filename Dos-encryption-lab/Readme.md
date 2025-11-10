# DoS Simulation & Secure Log Handling — Lab Report

**Short description:**  
Independent, lab-only exercises demonstrating controlled Denial-of-Service (DoS) simulations (HTTP & ICMP) and secure handling of resulting logs using symmetric (GPG) and asymmetric (RSA) encryption. All artifacts included are sanitized and intended for learning in a permissioned environment.

> ⚠️ IMPORTANT: All tests were executed in an isolated lab environment with permission. Do NOT attempt DoS attacks on public, third-party, or production systems.

---

## Project summary
This project documents controlled DoS testing and secure log-handling activities performed in a lab. Key activities:
- Simulated HTTP-based DoS (Metasploit test target) and ICMP flood tests from a Kali attacker VM.  
- Captured network traffic with **Wireshark** to verify destination IP, packet types (HTTP / ICMP), and continuous packet streams.  
- Monitored system behaviour on the target using `top` (observed CPU/memory increase during tests).  
- Created a sample operational log and demonstrated **symmetric** encryption (GPG) and **asymmetric** encryption (RSA public key) for secure storage and sharing.  
*(Based on internal lab exercise notes.)* :contentReference[oaicite:1]{index=1}

---

## What’s included
- **reports/dos-report.md** — narrative of DoS simulations, observations, and sanitized findings.  
- **reports/encryption-report.md** — steps and verification for GPG symmetric and RSA asymmetric encryption of logs (no passphrases or private keys included).  
- **images/** — sanitized screenshots referenced by reports (Wireshark captures, `top` output, GPG encrypt/decrypt screens).  
- **code/** *(optional)* — safe helper scripts (e.g., an example encryption script that reads passphrase at runtime).

---

## Evidence (sanitized)
- `images/wireshark-icmp.png` — Wireshark showing ICMP flood to `TARGET_IP` (IPs redacted).  
- `images/wireshark-http.png` — Wireshark showing HTTP request pattern (sanitized).  
- `images/top-target.png` — `top` snapshot showing CPU/memory rise on target during test.  
- `images/gpg-encrypt.png` — screenshot of `gpg --symmetric` (passphrase redacted).  
- `images/gpg-decrypt.png` — screenshot of successful GPG/RSA decryption (sanitized).

---

## High-level methodology (safe, non-actionable)
1. Prepare isolated lab: attacker VM (Kali) and target VM (Metasploit/test VM).  
2. Run controlled traffic tests; capture packets with Wireshark and monitor target with `top`.  
3. Record observations; create a sanitized log file (attack type, timestamp, attacker/target placeholders).  
4. Encrypt the log using `gpg --symmetric` (do not commit passphrase).  
5. Generate an RSA keypair locally (private key kept offline) and use the public key to encrypt the log for secure sharing; verify with the private key locally.

> Note: This README intentionally avoids attack commands or exploit scripts. It documents results only.

---

## How to reproduce (for reviewers)
- Use isolated VMs on a private network you control.  
- Use Wireshark to capture and `top` to observe system metrics.  
- Encrypt logs locally with `gpg --symmetric` (choose a secure passphrase and do not store it in the repo).  
- Use recipient public key for asymmetric encryption when sharing logs.

 

 

 

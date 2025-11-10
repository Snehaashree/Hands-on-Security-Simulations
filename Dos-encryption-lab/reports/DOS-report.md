# DoS Simulation — Lab Report (Sanitized)

**Scope & purpose**  
This document describes controlled Denial-of-Service (DoS) simulations performed in an isolated, permissioned lab environment. The goal was to observe network traffic characteristics and system behaviour under high-volume traffic conditions and to capture evidence for analysis. No exploit code or actionable attack tooling is published in this repository.

**Environment (lab-only)**  
- **Attacker:** Kali VM (lab)  
- **Target:** Metasploit / test VM (lab) — referred to below as `TARGET_IP` (sanitized)  
- **Monitoring tools:** Wireshark (network capture), `top` (system monitoring on target)  
- All activity was executed on an isolated network under supervision/permission.

---

## Objectives
1. Simulate and observe HTTP-based high-volume traffic against a local test target.  
2. Simulate and observe ICMP flood traffic against the same or another test target.  
3. Capture packet-level evidence with Wireshark showing destination IP, packet type, and continuous packet flow.  
4. Monitor system resource usage on the target (CPU / memory) during the tests.

---

## Methodology (high-level, non-actionable)
1. Prepare isolated test network with attacker VM and target VM.  
2. Start Wireshark on the monitoring host or on the attacker interface to capture traffic.  
3. Observe and record normal baseline behaviour on the target using `top`. Capture a baseline screenshot (`images/top-baseline.png`) if desired.  
4. Run controlled test traffic in the lab (short, supervised executions). Capture network traffic and system metrics while the test runs.  
5. Stop tests and collect captured PCAP or screenshots for analysis. Sanitize captures by redacting or replacing real IP addresses with `TARGET_IP` and `ATTACKER_IP`.

> Note: This document intentionally omits the commands/tools used to generate the test traffic. The focus is on observation, measurement, and defensive analysis.

---

## Evidence (sanitized screenshots)
- `images/wireshark-icmp.png` — Wireshark capture showing ICMP packet stream to `TARGET_IP`. The packet list shows repeated ICMP packets and the destination column indicates `TARGET_IP` (redacted).  
- `images/wireshark-http.png` — Wireshark capture showing HTTP request stream (many HTTP requests to `TARGET_IP`) during the simulated high-volume test.  
- `images/top-target.png` — `top` output on the target during the test showing increased CPU and memory usage compared to baseline.

Each screenshot in `images/` has been sanitized to remove real IPs, hostnames, and timestamps.

---

## Observations
- **Packet-level confirmation:** Wireshark captures clearly show `TARGET_IP` as the destination and the packet types (ICMP or HTTP) in a continuous stream consistent with high-volume traffic.  
- **System impact:** `top` snapshots taken during the tests show a notable increase in CPU utilization and (in some tests) memory pressure on the target VM compared to the baseline. Exact numbers vary by VM sizing and test intensity.  
- **Duration & continuity:** Captures show continuous packet streams over the test interval (evidence of traffic sustained for the window of capture).

---

## Analysis & implications
- The observed resource increase indicates that sustained high-volume traffic can degrade a target VM’s responsiveness. Even in a lab environment, this illustrates why production systems require mitigation: rate limiting, WAF rules, traffic shaping, and proper monitoring/alerting.  
- Packet captures (Wireshark) are effective for forensic validation — they show destination IP, protocol type, and stream continuity required for incident reports.

---

## Recommended mitigations (high-level)
- Implement network-level rate limiting and ingress filtering to reduce attack surface.  
- Configure firewalls to drop anomalous ICMP/HTTP patterns and use geo/IP reputation where appropriate.  
- Deploy an IDS/IPS to detect high-volume anomalies and trigger alerts.  
- Use traffic shaping or upstream scrubbing services for high-capacity mitigation.  
- Maintain forensic capture practices (PCAP retention, sanitized logs) for post-incident analysis.

---

## Ethics & authorization
All tests were executed in a controlled, permissioned lab. This report is for educational and defensive purposes only. Do not attempt DoS testing against systems you do not own or have explicit permission to test.

---

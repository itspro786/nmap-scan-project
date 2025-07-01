# 🔍 🛡️ Cybersecurity Internship – Task 1: Nmap TCP SYN Scan

## 📁 Project: Network Reconnaissance with Nmap

This project demonstrates how to scan a local network (`192.168.0.0/24`) using Nmap to discover active devices, open/closed/filtered ports, and analyze the potential exposure of services in a typical LAN environment.

---

## 🛠 Tools Used

- **Nmap** - For scanning network ports
- **Wireshark (Optional)** - For analyzing packet flow (TCP SYN packets)

---

## 📄 Commands Used

| Filename | Command | Purpose |
|----------|---------|---------|
| `nmap-sS-scan.txt` | `nmap -sS 192.168.0.0/24 -oN nmap-sS-scan.txt` | Stealth TCP SYN Scan across subnet |

---

## 🔎 Summary of Results

- **Total hosts up:** 60+
- **Filtered Ports:** Most ports were filtered, indicating firewalls or no active services.
- **Open Port:** Only `192.168.0.1` showed **port 1900 open** (UPnP).
- **Closed Ports Detected:** On IPs `192.168.0.8`, `.13`, `.18`, `.25` indicating listening services with no active connections.

### ⚠️ Potential Risks Identified:
- **Port 1900 (UPnP)**: Can leak device details if exposed externally.
- **Ports 500, 5989, 8800 (Closed)**: Commonly targeted for brute-force or exploit attempts.

---

## 📚 Concepts Demonstrated

| Concept | Explanation |
|--------|-------------|
| **TCP SYN Scan** | A half-open scan to detect open ports without completing handshake. Less detectable. |
| **Port Filtering** | If no response is received, the port is considered filtered (likely due to firewall). |
| **Closed Ports** | Indicate service is not listening, but host is reachable. |
| **Service Fingerprinting (Next Steps)** | Can use `-sV` and `-A` flags to fingerprint exact services for deeper enumeration. |

---

## 🔐 Recommendations

- Disable unnecessary services like UPnP.
- Apply firewall rules to filter untrusted traffic.
- Regularly scan internal networks to monitor device exposure.

---

## 📸 Optional Wireshark Screenshot
If packet capture was taken, upload it here.


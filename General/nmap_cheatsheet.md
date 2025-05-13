# Nmap Cheat Sheet (For CTFs)
---

## 1. 🔎 Full TCP Port Scan (Aggressive & Fast)

```bash
nmap --open -T5 -vvv --min-rate=300 --max-retries=3 -p- <IP>
```

### Explanation

- `nmap`: The network scanning tool used to discover hosts and services on a network.

- `--open`: Displays **only open ports** in the output. Useful for focusing on actionable results.

- `-T5`: Sets the **aggressiveness level** of the scan to 5 (the highest). This speeds up the scan but increases the chance of detection and inaccuracy on unstable networks.

- `-vvv`: Enables **very verbose output**. Shows detailed scan information in real time.

- `--min-rate=300`: Ensures that at least **300 packets per second** are sent. This speeds up the scan significantly.

- `--max-retries=3`: Limits the number of **retries per probe to 3**. This reduces the overall time taken by not retrying too many times.

- `-p-`: Tells Nmap to scan **all 65,535 TCP ports**, not just the default top 1000.

- `<IP>`: Replace this with the **target IP address** you want to scan.

---

## 2. 🔬 Service and Version Detection on Open Ports

```bash
nmap -sCV -p <open-ports> <IP>
```

### Explanation

- `-sC`: Runs **default scripts** (like checking HTTP titles, SSH banners, etc.).
- `-sV`: Enables **version detection**.
- `-p`: Provide the list of open ports found in the first scan (e.g., `-p 22,80,139,445`).
- Often run **after identifying open ports**.

---

## 3. 📜 Script Scan with Vulnerability Detection

```bash
nmap -sV --script vuln -p <open-ports> <IP>
```

### Explanation

- Scans known services on the target for **common vulnerabilities** using Nmap’s `vuln` scripts.
- Requires open ports and version detection.
- Great for finding low-hanging fruit vulnerabilities in CTFs.

---

## 4. 🚪 Top 1000 TCP Ports with Default Scripts

```bash
nmap -sC -sV <IP>
```

### Explanation

- Scans the **top 1000 ports** (default).
- Uses **default scripts** and version detection.
- A **quick and safe** starting point for initial enumeration.

---

## 5. 🕵️ Stealth SYN Scan (Default)

```bash
nmap -sS <IP>
```

### Explanation

- Performs a **stealth SYN scan** (half-open).
- Less likely to be detected by firewalls or logging.
- Fast and commonly used in CTFs.

---

## 6. 🎯 UDP Port Scan (Slow but Necessary)

```bash
nmap -sU -T4 --top-ports=50 <IP>
```

### Explanation

- Scans the **top 50 UDP ports** (adjustable).
- UDP scans are **slower and less reliable**, but essential for detecting services like DNS, SNMP, etc.
- Often overlooked, but sometimes critical in CTFs.

---

## 7. 📦 Scan Specific Port Range

```bash
nmap -p 1-1000 <IP>
```

### Explanation

- Scans ports **1 through 1000** only.
- Faster than full port scan.
- Can be useful if you're time-limited or want a **custom scan range**.

---

## 8. 🧠 Aggressive Scan with OS Detection

```bash
nmap -A <IP>
```

### Explanation

- Combines: `-sC`, `-sV`, OS detection, traceroute, and more.
- Very **comprehensive**, but also **noisy** and slower.
- Good for **in-depth enumeration**, but might be detected by defenses.

---

## Tips ✅

- Use `-Pn` if the host appears down but you're sure it's up:
  ```bash
  nmap -Pn -p- <IP>
  ```

- Save output for later:
  ```bash
  nmap -sC -sV -oN scan.txt <IP>
  ```

- Combine tools: After nmap, tools like `enum4linux`, `nikto`, `gobuster`, or `dirsearch` are great follow-ups depending on discovered services.

---

🎓 **Pro Tip for TryHackMe**: Start with a fast full port scan to catch unusual services, then follow up with more detailed scans targeting specific ports!


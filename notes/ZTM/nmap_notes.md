
# 🔥 Nmap Notes – By Gh0stSh3ll

## 🌐 What is Nmap?
- **Nmap (Network Mapper)** is a tool used for **network discovery** and **security auditing**.  
- Helps in finding hosts, open ports, services, versions, and even operating systems.  

---

## 🛠 Common Nmap Scans

### 1. SYN Scan (Stealth Scan)
- Command:  
  ```bash
  nmap -sS {target_ip}
  ```
- Sends SYN packets (like a handshake starter).  
- Faster, stealthy, and doesn’t complete the handshake.  

---

### 2. TCP Connect Scan
- Command:  
  ```bash
  nmap -sT {target_ip}
  ```
- Completes the **3-way handshake**.  
- Less stealthy (easily logged).  

---

### 3. UDP Scan
- Command:  
  ```bash
  nmap -sU {target_ip}
  ```
- Scans for open UDP services (e.g., DNS, SNMP, DHCP).  
- Slower because no handshake in UDP.  

---

### 4. Version Detection
- Command:  
  ```bash
  nmap -sV {target_ip}
  ```
- Identifies **service name & version** running on open ports.  

---

### 5. Aggressive Scan
- Command:  
  ```bash
  nmap -A {target_ip}
  ```
- Includes:
  - OS Detection  
  - Version Detection  
  - Script Scanning  
  - Traceroute  

---

### 6. OS Detection
- Command:  
  ```bash
  nmap -O {target_ip}
  ```
- Tries to guess the **Operating System** of the target.  

---

### 7. Specific Port Scan
- Command:  
  ```bash
  nmap -p 80,443,22 {target_ip}
  ```
- Scans only selected ports.  

---

### 8. Full Port Scan
- Command:  
  ```bash
  nmap -p- {target_ip}
  ```
- Scans **all 65535 ports**.  

---

### 9. Fast Scan
- Command:  
  ```bash
  nmap -F {target_ip}
  ```
- Scans top **100 common ports** (quick check).  

---

### 10. Host Discovery (Ping Sweep)
- Command:  
  ```bash
  nmap -sn {target_ip_range}
  ```
- Finds live hosts without scanning ports.  

---

### 11. Save Scan Results
- Commands:  
  ```bash
  nmap -oN output.txt {target_ip}   # Normal output
  nmap -oX output.xml {target_ip}   # XML output
  nmap -oG output.gnmap {target_ip} # Grepable
  ```

---

## ⚡ Pro Tips
- Use **root privileges** for advanced scans:  
  ```bash
  sudo nmap -sS -sV -O {target_ip}
  ```
- Combine multiple scans for better results.  
- Always scan **responsibly** (don’t hit random IPs).  

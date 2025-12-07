# 🧭 Hacking Methodology – Practical Ethical Hacking Notes

---

## 🔌 SMB (Ports 139 & 445)

- SMB is historically one of the **most vulnerable** services.

- First step: try **smbclient**  
  `smbclient -L \\{TARGET_IP}\\`

- `-L` lists all available shares.

- If anonymous login is enabled, you may see file listings without credentials.

- Use **Metasploit auxiliary scanners** to enumerate SMB versions.  
  (These modules fall under Scanning → Enumeration → Info Gathering)

- If Metasploit cannot identify the version, search manually on **Google** for known vulnerabilities.

---

## 📁 FTP (Port 21)

- Not highly exploitable by default.

- If FTP banner shows an old version, it *might* be vulnerable to a **buffer overflow**, but this is rare.

- If **anonymous login** is allowed:  
  - You may upload/download files,  
  - But exploitation opportunities are usually limited.

---

## 🔐 SSH (Port 22)

- SSH is **not usually exploitable** via direct version-based exploits.

- Very few practical SSH exploits exist.

- What *is* possible:
  
  - **Brute-force attacks**  
  - **Credential gathering** (from other compromised services)

- Attackers rarely target SSH as their first entry point.

---

## 🗂️ SMB Again (Ports 139/445)

- Known for **frequent historical vulnerabilities**.

- Always worth checking thoroughly because SMB misconfigurations often lead to full system compromise.

---

## 🌐 HTTP (Port 80) & FTP (Port 21)

- When you see HTTP open, **always visit the webpage** in a browser.

- Things to look for:
  
  - Default web pages  
  - Files hosted in unusual directories  
  - Poor security hygiene and outdated frameworks

- Perform **directory brute forcing**:

  - Tools: **Dirbuster**, **Gobuster**, **Dirb**

  - Purpose: discover hidden directories and entry points.

- FTP (if anonymous login enabled):  
  - Not very dangerous unless you can upload and **execute** files on the system.

---

# 🏴‍☠️ Core Takeaway

SMB and web services (HTTP/HTTPS) give the **most attack surface**, while SSH & FTP are less commonly exploited unless badly configured. Real attackers prioritize easy, misconfigured, or exposed services first.

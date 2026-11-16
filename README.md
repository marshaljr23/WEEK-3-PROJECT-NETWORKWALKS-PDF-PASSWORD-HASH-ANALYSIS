 <div align="center">

# 🔐 PDF PASSWORD HASH ANALYSIS

### Networkwalks tools, John the Ripper | PDF Password Recovery

**WEEK 03 — PROJECT MODULE 01**

![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=flat-square&logo=kalilinux&logoColor=white)
![John the Ripper](https://img.shields.io/badge/John_the_Ripper-000000?style=flat-square)
![Dictionary Attack](https://img.shields.io/badge/Dictionary_Attack-red?style=flat-square)
![Status](https://img.shields.io/badge/Status-Completed-00cc66?style=flat-square)


</div>

---

## 🟢 01. Mission Overview

This project demonstrates practical PDF password hash extraction and  dictionary-based password cracking using **Networkwalks PDF Password Extraction Tools and **John the Ripper**.

**Objective:** Extract the password hash from an encrypted PDF, perform a dictionary attack, recovered the password, and unlock the protected document to capture the flag.

| Mission Details | Information |
|---|---|
| Target | `My Locked PDF1, My Locked PDF1 (for NW Tools Lab WK3-PM2), My Locked PDF3 ` |
| Operating System | Kali Linux |
| Hash Extractor | Networkwalks Hashcalculculator, Onlinehashcrack |
| Cracking Tool | Networkwalks Extraction tools, John the Ripper |
| Wordlist | rockyou.txt |
| Attack Type | Dictionary Attack |
| Result | First Flag Captured |

## ⚡ 02. Attack Workflow

```mermaid
flowchart TD
    A[Encrypted PDF] --> B[My Locked PDF3, My Locked PDF1 (for NW Tools Lab WK3-PM2), My Locked PDF2]
    B --> C[Extracted Hash]
    C --> D[John the Ripper]
    E[rockyou.txt] --> D
    D --> F[Password Recovered]
    F --> G[Unlock PDF]
    G --> H[Flag Captured]

    style H fill:#006b35,color:#fff
    style D fill:#222,color:#fff
```

## 🛠️ 03. Tools & Technologies

| Tool | Purpose |
|---|---|
| Networkwalks Hashcalculator | Hash extraction and PDF Unlock|
| Networkwalks Hashcracker | PDF Password Crack|
| John the Ripper | Password cracking |
| rockyou.txt | Dictionary wordlist |

## 💻 04. Practical Execution

### Step 01 — Hash Extraction

Extracted the password hash from the encrypted PDF using Networkwalks Hashcalculator.

```bash
pdf2john "My Locked PDF1.pdf" > hash1.txt
```

### Step 02 — Wordlist Preparation

Decompressed the RockYou wordlist.

```bash
sudo gzip -d /usr/share/wordlists/rockyou.txt.gz
```

### Step 03 — Dictionary Attack
Cracked the Hashes using Networkwalks Hashcracker

<img width="1366" height="768" alt="PDF # Dehashed" src="https://github.com/user-attachments/assets/0da047d2-422c-4f8c-8de4-861d2583eafc" />

Executed John the Ripper against the extracted hash.

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt
```

### Step 04 — Password Recovery

Retrieved the recovered password.

```bash
john --show hash1.txt
```
<img width="1366" height="768" alt="JTR Password Hash-check" src="https://github.com/user-attachments/assets/380b9823-d731-46f0-84f6-a83e86214b73" />


### Step 05 — PDF Decryption

Used the recovered password to unlock the encrypted PDF and verify the flag.
<img width="1366" height="768" alt="PDF 2 Locked-A" src="https://github.com/user-attachments/assets/c3e193ec-91b0-4fbf-a73e-5ee5e4d3e72f" />



<badge color="success">MISSION COMPLETED — FLAG CAPTURED</badge>
<img width="1366" height="768" alt="PDF 2 Locked" src="https://github.com/user-attachments/assets/a28154d2-c518-4408-8cc0-40c8f596736b" />

## 📸 05. Evidence & Screenshots

| Terminal — Password Cracking | PDF — Flag Confirmation |
|---|---|
|<img width="1366" height="768" alt="Networkwalks Halcrack" src="https://github.com/user-attachments/assets/c0b666e2-4f34-4059-bd37-154a95c39ee5" />
 | <img width="1366" height="768" alt="PDF # Dehashed" src="https://github.com/user-attachments/assets/21be37f5-92c9-4730-af2a-6dd3676306af" />
|<img width="1366" height="768" alt="1q" src="https://github.com/user-attachments/assets/1d2f16de-21cb-44d1-ae05-b7adb61fed7b" />


## 🛡️ 06. Security Analysis

**Lessons**

- Understanding PDF password protection and hash extraction.
- Learning how offline dictionary attacks work.
- Using John the Ripper for password auditing.
- Understanding the risks of weak and predictable passwords.
- Applying stronger password practices and modern encryption.

**Recommendations**

- Use long and unique passwords.
- Avoid dictionary-based and predictable passwords.
- Use trusted password managers.
- Apply strong PDF encryption configurations such as AES-256.

## ⚠️ 07. Disclaimer

This project was performed strictly for educational and defensive cybersecurity learning purposes as part of the authorized **NETWORKWALKS** training program.

All activities were conducted in a controlled lab environment. Never attempt password cracking on files or systems without explicit authorization.

---

<div align="center">

### EMMANUEL OKO |Cybersecurity Intern | LinkedIn: https://www.linkedin.com/in/emmanuel-oko-234244199/ 

**Instructor:** WAQAS KARIM CCIE | **NETWORKWALKS** | Batch: **B084**  



</div>

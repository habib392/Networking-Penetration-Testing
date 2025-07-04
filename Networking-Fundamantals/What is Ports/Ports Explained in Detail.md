# What is Ports
---

## 📄 **Port, Service aur Vulnerability**

---

## 🔹 Port Kya Hota Hai?

Port server ka **digital darwaza** hota hai — jahan se data aata jaata hai.  
Har port ka ek number hota hai, jese 21, 22, 80, 443...  
Total ports hoti hain: **0 se 65535 tak**

---

## 📦 Port Number Categories:

| Range        | Kya Hota Hai              |
|--------------|---------------------------|
| 0 - 1023     | Well-known ports (default)  
| 1024 - 49151 | Registered (apps, tools)  
| 49152+       | Private ya dynamic ports  

---

## 🔌 Har Port Par Chalne Wali Services (Examples):

| Port | Service | Kaam |
|------|---------|------|
| 21   | FTP     | File transfer  
| 22   | SSH     | Secure remote login  
| 23   | Telnet  | Insecure remote login  
| 25   | SMTP    | Email bhejna  
| 53   | DNS     | Domain ka IP banaana  
| 80   | HTTP    | Website (non-secure)  
| 443  | HTTPS   | Secure website  
| 3306 | MySQL   | Database  
| 3389 | RDP     | Remote desktop

---

## ❓ Kya Port Website Mein Use Hoti Hai?

✅ Haan!  
Jab tu kisi website ko open karta hai to browser actually **port 80 ya 443** pe request bhejta hai.

| Port | Kya karta hai?         |
|------|------------------------|
| 80   | Normal HTTP website  
| 443  | Secure HTTPS website

Agar dono band hain to browser error dega: `Site can’t be reached`

---

## 🔍 Custom Port Par Website?

Kabhi kabhi website **dusre port pe bhi chalti hai** jese:
- `8080`, `8000`, `8443`, `3000`

➡️ Tu check kar sakta hai:
```bash
nmap -p 1-10000 target.com
````

Phir try kar:

```
http://target.com:8080
```

---

## ❌ Port Open Hona = Vulnerable Nahi

Open port sirf yeh batata hai ke koi service chal rahi hai
Lekin agar wo service **vulnerable ya misconfigured** hai to hi attack possible hota hai.

---

## 💣 Common Vulnerable Ports:

| Port | Service | Kya Attack Hota Hai?    |
| ---- | ------- | ----------------------- |
| 21   | FTP     | Anonymous login         |
| 22   | SSH     | Brute force             |
| 23   | Telnet  | Sniffing, no encryption |
| 80   | HTTP    | XSS, SQLi, CSRF         |
| 445  | SMB     | EternalBlue             |
| 3306 | MySQL   | Default passwords       |
| 3389 | RDP     | Remote exploit          |
| 8080 | Web     | Exposed admin panels    |

---

## ⚙️ Configuration (Config) Kya Hota Hai?

**Config = Settings file** jo service chalane ka tareeqa batati hai.

| Service | Weak Config        | Secure Config  |
| ------- | ------------------ | -------------- |
| FTP     | Anonymous login ON | OFF            |
| SSH     | Root login allowed | Blocked        |
| Web App | Debug mode ON      | OFF            |
| DB      | Public access      | Localhost only |

➡️ Agar config weak ho to attack asaan hota hai

---

## 🔎 Vulnerability Kaise Pata Karein?

### ✅ Step-by-Step:

1. Nmap se scan karo:

```bash
nmap -sV target.com
```

2. Version note karo:

```
21/tcp open  ftp     vsftpd 2.3.4
```

3. Check karo yeh version vulnerable hai ya nahi:

```bash
searchsploit vsftpd 2.3.4
```

Ya search karo:
`vsftpd 2.3.4 vulnerability` on Google or Exploit-DB

4. CVE milta hai to exploit ka chance 70-80% hota hai

5. Agar config bhi weak ho → **Boom! Attack successful**

---

## 📌 Final Summary:

| Cheez         | Matlab                           |
| ------------- | -------------------------------- |
| Port Open     | Service chal rahi hai            |
| Version Found | Vulnerability check kar sakte ho |
| Vulnerable    | Exploit possible                 |
| Secure Config | Attack rok sakta hai             |
| Weak Config   | Shell mil sakta hai 😈           |

---

## 🔧 Tere Tools:

| Tool             | Kaam                          |
| ---------------- | ----------------------------- |
| `nmap -sV`       | Port + version detect         |
| `searchsploit`   | Version ka exploit dhoondhna  |
| `exploit-db.com` | Online exploit search         |
| `hydra`          | Brute force login             |
| `Burp Suite`     | Web config & vuln test        |
| `nc`, `telnet`   | Banner grabbing (manual test) |

---

## 🚀 Habib's Pentesting Style:

1. Nmap se scan kar
2. Version check kar
3. Exploit dhoondh
4. Config test kar
5. Attack launch kar
6. 🎯 Result: Shell mil gaya to WIN!

---

🧠 **Yaad Rakh: Port khula hona sirf chance hai,
Version aur config batate hain ke tu andar jaa sakta hai ya nahi.**

---

📌 **End of Note — Ports ka level complete!
Tayyar ho agle mission ke liye? 😎**

```
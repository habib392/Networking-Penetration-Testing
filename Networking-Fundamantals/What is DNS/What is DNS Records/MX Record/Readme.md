### 🔹 MX Record Kya Hota Hai?

**MX ka matlab hota hai "Mail Exchange"**.

Yeh DNS ka aik record hota hai jo batata hai ke **kis server pr ek domain ka email system kaam kar raha hai**.

---

### 🔹 Real Life Example:

Agar koi banda yeh email bhejta hai:

📧 `support@paksecurity.com`

Toh system ko yeh dekhna hota hai:

* "paksecurity.com" ka email kis server pr deliver hoga?

**Yeh kaam DNS karta hai, jahan MX record hota hai** jo batata hai ke:

> `paksecurity.com` ka email server kaunsa hai (jaise mail.google.com, mail.zoho.com, etc)

---

### 🔹 MX Record Mein Kya Hota Hai?

MX record 2 cheezen deta hai:

1. **Priority (number)** – Jitna chhota number, utni zyada priority.
2. **Mail Server Hostname** – Email kaha bhejna hai.

---

### 🔹 Example:

| Priority | Mail Server             |
| -------- | ----------------------- |
| 10       | `mail1.paksecurity.com` |
| 20       | `mail2.paksecurity.com` |

Yani pehlay email **mail1** par jaayegi. Agar wo down hua, to backup **mail2** pr chali jaayegi.

---

### 🔹 MX Record Se Penetration Testing Ka Kya Taluk?

Agar tum kisi website ka **MX record** nikal lo:

```bash
dig MX paksecurity.com
```

Ya:

```bash
nslookup -query=mx paksecurity.com
```

To tumhe pata lag sakta hai:

* Wo **Google Workspace use kar raha hai** ya apna khud ka mail server.
* Agar outdated mail server laga hua hai, usme misconfiguration ya open relay kaam aa sakta hai.
* Kabhi kabar **email spoofing** ya phishing ke liye bhi misused ho sakta hai agar SPF/DKIM records nahi hain.

---

### 🔹 Real World Use Case:

Tum `target.com` ka MX record check karte ho aur milta hai:

```
Priority: 10
Server: mail.target.com
```

Phir tum `mail.target.com` pr port scan karte ho (like `nmap -p 25,110,143 mail.target.com`) aur pata chalta hai:

* Port 25 (SMTP) open hai
* Server banner: "Sendmail 8.13 (2006)"
  Ye outdated hai → **Vulnerable ho sakta hai to exploits**.

---

### 🔹 Short Summary:

| Term         | Explanation                                  |
| ------------ | -------------------------------------------- |
| MX Record    | Batata hai email kahan bhejna hai            |
| Priority     | Lower value = higher priority                |
| Email Attack | Misconfigured MX server = phishing/spoofing  |
| Tool         | `dig`, `nslookup`, `host` for reconnaissance |

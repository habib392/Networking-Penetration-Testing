PTR Record ka matlab hai: **Pointer Record**

Yeh DNS ka **reverse lookup record** hota hai.
Matlab normally hum domain se IP nikalte hain — `A record`.
Lekin PTR record se **IP address se domain name** nikalte hain.

---

### 💡 Samajhne ka Tareeqa:

* `A Record`: `example.com` ➜ `192.168.1.1`
* `PTR Record`: `192.168.1.1` ➜ `example.com`

---

### ⚙️ Real Life Example:

Socho tumhari website hai `bank.com`, aur koi tumhara server access kar raha hai via IP `203.0.113.45`.
Ab tum chahte ho verify karna ke kya yeh IP waqai kisi trusted domain se aayi hai?

🔹 Tum reverse DNS lookup karwao ge:

```bash
nslookup 203.0.113.45
```

Agar PTR record set hoga, output ayegi:

```
45.113.0.203.in-addr.arpa name = google.com
```

Matlab `203.0.113.45` ➜ `google.com`

---

### ✅ Use Cases:

1. **Email Servers Verification (SPAM protection)**
   Jab email server (e.g. Gmail) kisi IP se mail receive karta hai, woh **PTR record check** karta hai ke IP kis domain se linked hai.
   Agar PTR set nahi hoga to email spam mein chala jata hai.

2. **Log Monitoring / SIEM**
   Jab kisi IP ne attack kiya ho, SIEM tools IP se domain nikal k **threat intelligence** mein use karte hain.

---

### 🛡 Penetration Testing mein Kaise Kaam ka?

1. **Footprinting/Recon**
   Jab tum kisi IP range per scan karo, aur `PTR record` mil jaye, to tumhe pata chal sakta hai ke woh IP kis domain se related hai.

   Example:

   ```
   nmap -sL 192.168.1.0/24
   ```

   Ye command IPs ke liye reverse DNS try karegi.

2. **Finding Misconfigured Servers**
   Kabhi kabhi dev/test servers ke PTR records hotay hain jisme secret info hoti hai:

   ```
   13.37.21.10.in-addr.arpa name = dev-beta-api.bank.internal
   ```

   Bas iss info se tum jaan gaye ke internal server ka naam kya hai.

---

### 🧠 Extra Tip:

* PTR record hamesha `reverse zone` mein banta hai.
  Jaise: `1.0.168.192.in-addr.arpa` ➜ `habib.com

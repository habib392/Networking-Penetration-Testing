## ✨ DNS Kya Hai?

Jab hum kisi website ka domain likhtay hain jaise `garena.com`, toh browser ko uska IP address chahiye hota hai takay woh website open kar sake. DNS ka kaam hota hai **domain name ko IP address mein convert karna**. Server sirf IP samajhta hai, naam nahi. DNS ek translator ka kaam karta hai.

---

## 🔹 A Record (Address Record)

Jab hum koi domain name purchase karte hain, phir us domain ko chalane ke liye hume ek server chahiye hota hai (jaise ek alag computer jo 24/7 chalta rahe). Server hume IP address deta hai. Hum A record ki madad se domain name ko is IP address ke sath jor dete hain.

**Example:**

```
garena.com → 104.20.23.45
```

Jab koi user `garena.com` likhta hai, DNS A record use karke browser ko IP deta hai jahan website host hai.

---

## 🔹 AAAA Record

Ye bilkul A record jaisa hai, bas ye IPv6 IP address use karta hai. Aaj kal zyadatar websites IPv4 use karti hain lekin future ke liye IPv6 important hai.

**Example:**

```
example.com → 2606:4700:3035::6815:514
```

---

## 🔹 CNAME Record (Canonical Name)

Ye aik alias ya nickname hota hai. Jab website par kaam chal raha hota hai aur developer chahta hai ke users ko alternate version dikhe, toh woh domain ko kisi aur domain ya subdomain par redirect kar deta hai CNAME se.

**Example:**

```
www.garena.com → garena.com
maintenance.garena.com → garena2.com
```

Jab hum `www.garena.com` likhte hain, woh `garena.com` ya kisi aur domain pe chala jata hai backend mein.

---

## 🔹 MX Record (Mail Exchange)

Jab hum apni website ke liye domain purchase karte hain, toh hum chahte hain ke humara email system bhi ho, jaise:

```
habib@garena.com
admin@garena.com
support@garena.com
```

MX record batata hai ke ye emails kis mail server par jayengi.

**Example:**

```
garena.com → mail.garena.com (via MX Record)
```

Agar hum Google Workspace ya Zoho Mail use karna chahein toh woh hume MX records set karne ko kehta hai:

```
ASPMX.L.GOOGLE.COM
```

**Note:** MX record change karke aap `@yourdomain.com` par Gmail ke through email chala sakte ho, lekin `@gmail.com` banana possible nahi hai.

---

## 🔹 TXT Record (Text Record)

Ye record kisi bhi tarah ka text data rakh sakta hai, lekin normally ye security aur verification ke liye use hota hai. Developer koi bhi text nahi likhta apne man se.

**Real-Life Use Cases:**

* **SPF Record:** Kis server ko email bhejne ki permission hai
* **DKIM:** Email signature verify karta hai
* **DMARC:** Email policy batata hai
* **Google Verification:** Google Search Console verify karta hai

**Example:**

```
v=spf1 include:_spf.google.com ~all
```

```
google-site-verification=abc123xyz
```

---

## 🔹 NS Record (Name Server)

Jab hum domain purchase karte hain, hume uska control kisi DNS provider ko dena padta hai. NS record batata hai ke domain ka DNS system kaun handle karega.

**Example:**

```
garena.com → ns1.cloudflare.com
                ns2.cloudflare.com
```

Cloudflare ek DNS provider bhi hai (saath hi CDN aur firewall bhi deta hai). Zyada NS hone ka faida hota hai agar DDoS ya server down ho jaye toh backup NS handle karta hai.

---

## 🔹 PTR Record (Pointer Record)

Ye reverse DNS ke liye hota hai. Matlab agar humare paas sirf IP address hai, toh hum dekh sakte hain ke ye IP kis domain se linked hai.

**Example:**

```
192.0.2.55 → mail.habibsecurity.com
```

Ye zyada tar email spam detection mein use hota hai. Agar PTR aur A record match nahi karte, toh email spam folder mein chali jati hai.

---

## 🔹 SOA Record (Start of Authority)

Ye zone file ka head hota hai. Isme hoti hai:

* Domain ka admin ka email
* Last update ka time
* Zone serial number

Agar koi problem aaye DNS mein toh SOA record se pata chalta hai kahan issue hai aur kisse contact karna hai.

---

## 🔹 SRV Record (Service Record)

Ye batata hai ke kisi service (jaise VOIP, chat, Microsoft Teams) kaunsa port aur host use karta hai.

**Example:**

```
_sip._tcp.example.com → 10 60 5060 sipserver.example.com
```

Pentesting ya recon mein ye service scanning mein kaam aata hai.

---

## 🔹 CAA Record (Certificate Authority Authorization)

Ye batata hai ke kaunsi SSL certificate authority is domain ke liye certificate issue kar sakti hai. Isse attacker fake SSL certificate nahi bana sakta.

**Example:**

```
CAA: only letsencrypt.org allowed
```

---

## 🔧 Penetration Testing Mein DNS Records ka Use:

| Record   | Faaida                                |
| -------- | ------------------------------------- |
| A / AAAA | Subdomain discovery                   |
| CNAME    | Backend ya dev servers discover karna |
| MX       | Mail server enumeration, spoof check  |
| TXT      | SPF/DKIM misconfig find karna         |
| NS       | Zone transfer attack ya DNS mapping   |
| PTR      | Reverse lookup, mail security         |
| SOA      | Zone info nikalna                     |
| SRV      | Service ports aur targets pata karna  |
| CAA      | SSL bypass ya fake cert attempt check |

---

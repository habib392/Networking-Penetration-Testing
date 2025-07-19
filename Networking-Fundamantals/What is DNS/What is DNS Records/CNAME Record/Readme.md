## 🔹 CNAME Record – Root se Samajho:

**CNAME** ka matlab hai: **Canonical Name**.

Iska kaam hai:
➡️ **Ek domain ko kisi doosray domain ka alias banana**.
Matlab: Aap ke paas aik naam hai, lekin asli location ya IP kisi doosray naam se linked hai.

---

## 📘 Real Life Example:

Suppose:

* Aapka subdomain hai: `blog.habib.com`
* Lekin aap blog ko host kar rahe ho **Medium.com** pe ya kisi 3rd party service pe
* To aap `blog.habib.com` ke liye **CNAME** record set kar do:

```
blog.habib.com -> habib.medium.com
```

Ab jab koi `blog.habib.com` par jaaye ga, DNS usay `habib.medium.com` par redirect kare ga.
**Lekin browser mein URL same `blog.habib.com` hi rahe ga**.

---

## 💥 Penetration Testing Main Iska Use:

### 1. 🔍 **Subdomain Takeover**

CNAME record ka sabse bada risk hai:

> **Subdomain Takeover Attack**

#### Scenario:

* Client ne `app.client.com` ka CNAME banaya `clientapp.herokuapp.com` par
* Lekin wo `clientapp.herokuapp.com` delete kar diya
* Ab attacker same naam ka app create kar leta hai Heroku pe
* **Boom!** `app.client.com` attacker ke control mein aa gaya

Yeh **real vulnerability** hai. Bug bounty programs mein is kaafi high impact hota hai.

#### 🧪 Tools for Testing:

* `subjack`, `Subzy`, `tko-subs`, etc.
* Aap `dig`, `nslookup`, ya `host` se manually bhi dekh saktay ho

### 2. 🛠️ **Reconnaissance**

CNAME se pata lagta hai:

* Kon si 3rd party service use ho rahi hai (Shopify, Heroku, GitHub Pages, AWS S3)
* Iska matlab aapko **infrastructure mapping** mein madad milti hai

#### Example:

```bash
dig CNAME blog.habib.com
```

Output:

```
blog.habib.com.  300  IN  CNAME  habib.medium.com.
```

Aap jaante ho ke Medium use ho raha hai. Ab aap Medium ki misconfigurations explore kar saktay ho.

---

## 🧠 Short Summary:

| Term                | CNAME Record                                    |
| ------------------- | ----------------------------------------------- |
| Kya karta hai?      | Ek domain ko doosray domain ka alias banata hai |
| Real-life use       | blog.example.com -> Medium, Shopify, etc.       |
| Pentesting main use | Subdomain takeover, 3rd party infra recon       |
| Risk                | Deleted target domain = takeover                |

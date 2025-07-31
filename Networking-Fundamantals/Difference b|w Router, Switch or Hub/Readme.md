### **Hub, Switch, aur Router ka Comparison**

---

### **Hub Kya Hai aur Kaisy Kaam Karta Hai?**

1. Hub aik simple network device hoti hai.
2. Agar is se 5 devices connected hain (wired ya wireless), aur koi aik device data send karta hai...
3. ...toh hub woh data **sabhi devices ko broadcast** kar deta hai.
4. Matlab agar device 1 sirf device 3 ko data bhejna chahta hai, phir bhi hub **device 2, 4, aur 5** ko bhi wohi data bhej deta hai.
5. Is wajah se **data secure nahi hota** aur **network slow** ho sakta hai.
6. Penetration testing mein hub wale network mein sniffing (data chori) easy hoti hai Wireshark jaisy tools se.

---

### **Switch Kya Hai aur Kaisy Kaam Karta Hai?**

1. Switch hub se zyada smart device hai.
2. Jab 5 devices switch se connected hon, aur device 1 sirf device 4 ko data bhejna chahta ho...
3. ...toh switch **sirf device 4 ko data send** karta hai.
4. Baqi devices ko data nahi milta, is se **network fast** rehta hai aur **privacy barhti hai**.
5. Switch MAC address table maintain karta hai — har device ka address samajh kar **targeted communication** karta hai.
6. Penetration testing mein agar aapko switch network sniff krna hai, toh aapko ARP Spoofing ya MITM attacks karne padte hain.

---

### **Router Kya Hai aur Kaisy Kaam Karta Hai?**

1. Router multiple networks ko aapas mein connect karta hai.
2. Jaise ghar ka network internet se router ke zariye connect hota hai.
3. Router har device ko ek private IP deta hai (jaise 192.168.x.x).
4. Agar device 1 internet par YouTube kholta hai, toh router data **internet tak le jaata hai** aur wapas bhi lata hai.
5. Router ke through data ya toh **broadcast** ho sakta hai ya **specific device** ko bheja ja sakta hai — depends on configuration.
6. Router IP addresses handle karta hai aur **data ka best path** decide karta hai.
7. Penetration testing mein router configuration misconfigure ho toh aap DNS poisoning, routing attacks, ya remote access try kar saktay ho.

---

### **Step 4: Summary (Ek Nazar Mein Farq):**

| Device     | Kya Karta Hai                | Broadcast/Data Handling  | Pentest Point       |
| ---------- | ---------------------------- | ------------------------ | ------------------- |
| **Hub**    | Sab ko data deta hai         | Sab devices ko data      | Easy sniffing       |
| **Switch** | Sirf target ko data deta hai | Selective (based on MAC) | MITM required       |
| **Router** | Networks connect karta hai   | IP-based routing         | DNS/Routing attacks |

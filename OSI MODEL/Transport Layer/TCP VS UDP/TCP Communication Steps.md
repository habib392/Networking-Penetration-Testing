## 📚 **TCP (Transmission Control Protocol)**

---

### 🔸 TCP/UDP Kaam Kya Karte Hain?

Jitna bhi data duniya mein ek computer se doosre tak jaata hai — woh ya to **TCP** ya **UDP** ke through jaata hai.

Har data **packets** mein divide hota hai aur har packet ek **rasta (port)** se guzarta hai.
TCP/UDP rules follow nahin kiye gaye to packets **drop** ho jaate hain.

---

## 🔹 TCP ke 6 Flags – Real Explanation:

| Flag    | Matlab                                         | Use                              |
| ------- | ---------------------------------------------- | -------------------------------- |
| **SYN** | Connection banane ka signal                    | “Bhai baat karni hai.”           |
| **ACK** | Message mil gaya                               | “Haan bhai, teri baat mil gayi.” |
| **PSH** | Data buffer mein na rakho, turant process karo | Voice call, online gaming        |
| **URG** | Emergency data hai, pehle process karo         | Telnet interrupt (CTRL+C)        |
| **FIN** | Connection politely band karo                  | “Main call rakh raha hoon.”      |
| **RST** | Abruptly connection band karo                  | “Line kaat do turant!”           |

---

### ✅ 3-Way Handshake (Connection Banna)

**Real-Life Example: Phone Call Start**

1. **SYN**: Client bolta hai – “Call karoon?”
2. **SYN+ACK**: Server bolta hai – “Haan, karo + tumhari call mujhe aayi.”
3. **ACK**: Client bolta hai – “Theek hai, call shuru kar di.”

> Isay kehte hain **Three-Way Handshake** – TCP connection establish karne ka tareeqa.

---

### ✅ PSH Flag – Real-World Use

**Scenario**: WhatsApp pe **voice call** ya **live stream**

> PSH ka matlab: "Data turant app ko dedo, ruk ke buffer mat karo."

🕹️ Games, 🎙️ Live audio, 📞 Voice calls mein PSH use hota hai.

---

### ✅ URG Flag – Real-World Use

**Scenario**: Telnet session mein user **CTRL+C** karta hai

> URG ka matlab: “Yeh data normal queue se pehle bhejna hai — sab kaam chhoro, yeh urgent hai.”

Rare use hota hai — mostly system-level interrupts ya control commands mein.

---

### ✅ TCP Session Termination – 4 Way Handshake

**Real-Life Example: Call Band Karna**

1. **FIN (Client → Server)**: “Main call band kar raha hoon.”
2. **ACK (Server → Client)**: “Theek hai, samajh gaya.”
3. **FIN (Server → Client)**: “Main bhi call band kar raha hoon.”
4. **ACK (Client → Server)**: “Done, call band ho gayi.”

> Yehi hota hai **4-Way Handshake** – connection ka polite end.

---

### ❗ FIN vs RST – Samajh Lo

| Type    | Matlab                         | Real-Life                  |
| ------- | ------------------------------ | -------------------------- |
| **FIN** | Connection **gracefully** band | “Salam ke sath call band”  |
| **RST** | Connection **zabardasti** band | “Call kaat di bina bataye” |

---

## 💥 Penetration Testing Tips:

✅ **Sniff** karo TCP flags Wireshark se:

* PSH → Real-time traffic detect karo
* URG → Control signals samjho
* RST → Server-side errors ya rejection pakdo

✅ **FIN Flood**, **RST injection**, ya **Session Hijacking** ke liye ye base understanding must hai.

---

## 🧠 Final Thoughts:

> “TCP samajhna web security ki foundation hai — har login, form, API call ka base yehi hai.”

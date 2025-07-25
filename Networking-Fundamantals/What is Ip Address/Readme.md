IP Address Guide

Author: Habib Date: 2025-07-16


---

1. IP (Internet Protocol) kya hai?

IP address ek unique numeric label hai jo har device ko network mein identify karta hai.

IPv4: 32-bit address (4 bytes) e.g. 123.11.24.13

~4.3 billion addresses


IPv6: 128-bit address (16 bytes) e.g. 2001:0db8:85a3:0000:0000:8a2e:0370:7334

340 undecillion addresses


2. IPv4 ki details

1. Structure: 4 parts (bytes), har part 0–255

---

2. Parts Meaning:

1st byte → Country/region

2nd byte → State/area

3rd byte → ISP

4th byte → Device

---

3. Types of IP addresses:

Public IP: ISP se milta hai (Jazz, Zong, Telenor)

Private IP: Router LAN mein allocate karta hai (192.168.x.x, 10.x.x.x)

Static IP: IP address jo kabhi change nahi hota. Usually servers ya CCTV DVRs ko diya jata hai. Purchase karna padta hai.

Dynamic IP: Har baar router ya ISP se naye session pe naya IP milta hai. Home users mostly isi ko use karte hain.


---

4. IPv6 ka overview

Format: 8 blocks, har block 16 bits (4 hex digits)

Example breakdown:

2001:0db8:85a3:0000:0000:8a2e:0370:7334

Block	Function

- 2001	Global network prefix
- 0db8	Example/documentation network
- 85a3	Subnet info
- 0000	Reserved/subnet
- 0000	Reserved
- 8a2e	Interface ID part
- 0370	Interface ID
- 7334	Interface ID last part


Compression: 0000 blocks ko :: se replace

e.g. 2001:0db8::1


Hexadecimal: digits 0–9, a–f

---

5. Penetration Testing mein IP ka use

Recon: nmap, traceroute se network map karna

Host header attacks: real server IP find karke direct attack

WAF/Ratelimit bypass: X-Forwarded-For spoof karke

IPv6 vectors: tunneling attacks, misconfigured DNS

---

6. Website ka IP address kaise nikaale?

1. Command line tools:

```ping example.com```

```nslookup example.com```

```dig example.com```

```host example.com```

---

2. Online tools: DNSDumpster, SecurityTrails, crt.sh


3. Recon frameworks: nmap scripting, Amass, Sublist3r

---

7. X-Forwarded-For header

Client ka original IP jab proxy/load balancer use hota hai

Burp Suite request mein modify karke WAF/Ratelimit bypass:
```
GET / HTTP/1.1
Host: target.com
X-Forwarded-For: 127.0.0.1
```
---

8. Q&A summary

Hacker trace: IPv4 aur IPv6 dono trace ho sakte hain, but VPN/TOR use common

Location accuracy: IPv6 detailed blocks, magar exact location tab bhi ISP se hi milti hai

PenTest process: server logs, timestamps, ISP logs, legal warrant


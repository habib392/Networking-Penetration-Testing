## Ports

### 1. Ports Kya Hain?

* **Port** matlab rasta jahan se data packets travel karte hain.
* Jaise ghar se Dost ke ghar 2km dur, raaste banaye gaye - woh raaste = ports.
* Networking mein 65535 ports hote hain.

### 2. Port Types

1. **Well-known Ports (0–1023)**

   * Reserved OS-level services.
   * Examples: HTTP (80), HTTPS (443), FTP (21), SSH (22).
2. **Registered Ports (1024–49151)**

   * Software companies register yeh ports.
   * Examples: MySQL (3306), PostgreSQL (5432).
3. **Dynamic/Ephemeral Ports (49152–65535)**

   * Temporary connections ke liye.
   * Client apps (Chrome, Memu, games) yeh range se random port use karte hain.

### 3. Rule #1: Unique Port Binding

* **Server apps** (jo "listen" karte hain) ek hi port pe ek hi time pe bind kar sakte hain.
* Agar do servers same port + same IP + same protocol bind karne ki koshish karein:

  * Error: `Port 80 is already in use`.
* **Client apps** dynamic source ports use karte hain, isliye chrome + Memu ek hi server port (443) pe request bhej sakte hain - no conflict.

### 4. Rule #2: Port Identifies Service

* Port number batata hai kaun si service se connection ban raha hai.
* Browser `http://example.com` -> destination port 80.
* FTP client -> destination port 21.

### 5. Dynamic Ports: Example

* Jab Chrome website kholta hai:

  * Source (tuhara PC) = random port e.g. 50124
  * Destination (server) = 443
* Jab Memu Play internet use karta hai:

  * Source = random port e.g. 50126
  * Destination = 443

### 6. Error Kab Aata Hai?

1. **Duplicate Server Binding**

   * Apache + XAMPP dono port 80 pe "listen" -> conflict.
2. **Firewall/Antivirus Block**

   * Agar firewall port block kare -> `Connection timed out`.
3. **Router NAT Conflict**

   * Port forwarding same port pe multiple devices -> bind error.

### 7. Penetration Testing Tip

* **Port Scanning**:

  * `nmap -p- <target>` se jaan lo open ports.
  * Jis port pe service chal rahi ho, wahan se attack vectors explore karo.

### 8. Commands for Live Check (Windows)

* `netstat -an` - active connections & listening ports.
* `tcpview` tool - GUI mein port use dekho.

---

#### Poori Conversation Points

1. Ports = raste jahan se data travel kare.
2. Total 65535 ports; 3 types: well-known, registered, dynamic.
3. Rule #1: Sirf server apps binding mein unique.
4. Rule #2: Port se service identify.
5. Client apps dynamic source ports use karte.
6. Example: Chrome, Memu Play, GTA case.
7. Error cases: duplicate server bind, firewall block, NAT conflict.
8. PenTest tip: nmap, netstat, ss, tcpview.


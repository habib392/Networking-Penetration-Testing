# MAC Address (Media Access Control) Guide

---

## 1. MAC Address kya hota hai?

* MAC (Media Access Control) address ek **unique hardware identifier** hota hai jo har network-enabled device (jaise mobile, laptop, router, etc.) ko diya jata hai.
* Ye har device ke **network interface card (NIC)** ke andar hard-coded hota hai.
* MAC address ke zariye local network mein har device ko pehchana ja sakta hai.

## 2. MAC Address ka Format

* MAC address hota hai **48-bit ya 6 bytes** ka.
* Format: 6 pairs of hexadecimal numbers, colon (:) ya hyphen (-) se separate hotay hain.

  * Example: `3C:5A:B4:9A:77:01`

## 3. MAC Address ke Do Hisse

| Part          | Explanation                                                                                                                                                                   |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| First 3 Bytes | **OUI (Organizationally Unique Identifier):** Yeh batata hai ke device kis company ne banaya. Yeh identify karta hai country, state ya manufacturer (jaise Samsung, Oppo, HP) |
| Last 3 Bytes  | **NIC Specific:** Device-specific hota hai — har hardware ka unique part, jisse trace possible hota hai                                                                       |

## 4. Real-World Example:

* Habib ke paas ek OPPO A31 phone hai.
* Duniya mein aur bhi OPPO A31 phones honge, lekin har phone ka MAC address alag hoga.
* Is OPPO A31 ka MAC address ho sakta hai `D0:F1:02:3B:4C:5D`

  * `D0:F1:02` → OPPO company ka code (OUI)
  * `3B:4C:5D` → Device-specific unique code

## 5. MAC Address Lookup

* Kisi bhi device ka MAC address dekhne ke liye lookup tools use kar sakte ho:

  1. Google: `mac address lookup`
  2. Websites: `macvendors.com`, `dnschecker.org/mac-lookup`
  3. Wahan MAC address paste karo → Manufacturer, vendor aur kabhi kabhi location bhi milti hai

## 6. MAC vs IP Address

| Feature     | MAC Address                  | IP Address                    |
| ----------- | ---------------------------- | ----------------------------- |
| Layer       | Data Link Layer (Layer 2)    | Network Layer (Layer 3)       |
| Changeable? | Normally no (hardware fixed) | Yes (dynamic/static)          |
| Use         | Local network communication  | Internet/global communication |
| Visibility  | Local router/tap par visible | Globally visible (via ISP)    |

## 7. Penetration Testing mein MAC ka role

* **Local Network Attacks:**

  * ARP Spoofing / Poisoning
  * MAC Filtering Bypass (spoof another MAC)
* **Device Fingerprinting:** Kisi device ka MAC mil jae toh uski identity trace kar sakte hain (especially in internal network).
* **Recon in LAN:** Wireless sniffing tools (e.g., Wireshark, airodump-ng) MAC address show karte hain

## 8. MAC Address Spoofing

* MAC address ko spoof (change) bhi kiya ja sakta hai — Linux aur Kali Linux mein yeh common technique hai:

  ```bash
  ifconfig eth0 down
  macchanger -r eth0
  ifconfig eth0 up
  ```
* **Use Case:**

  * School/college Wi-Fi bypass
  * Device bans se bachna
  * Anonymity in local sniffing

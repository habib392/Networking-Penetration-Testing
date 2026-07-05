# What is ARP

ARP (Address Resolution Protocol) aik aisa protocol hai jo network pr connect sub devices ky ip address ky zariye iun ka MAC Address find krta hai.

### Asan alfaz main

Yani aik router hai jis sy 5 devices connected hain, router ny subko aik aik private ip address dy rakha hai or iska record ARP ky pass hai. Ab ARP inn IP addresses ky zariye sub devices sy iun ka MAC Address pochta hai or save krta hai.

Router ya koi bhi device jab aik baar ARP ke zariye kisi ka MAC address pooch leti hai, to woh use baar-baar nahi poochti. Woh us record ko apne paas aik temporary diary mein save kar leti hai, jise hum ARP Table ya ARP Cache kehte hain.


​Jab aap terminal par arp -a command chalayein ge, to aap ko aap ke computer ki wahi diary nazar aayegi jismein connected devices ke IPs aur un ke hardware MAC addresses save hotay hain.
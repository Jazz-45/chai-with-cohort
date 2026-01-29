
# DNS Record Types Explained

## DNS Recap: What DNS Is and Why It Exists

When you type a website name like [`google.com`](http://google.com/) into a browser, the computer cannot understand that name directly. Computers only understand IP addresses, which are numbers.

DNS (Domain Name System) solves this problem. It works like the phonebook of the internet, converting human-friendly website names into machine-readable IP addresses.

Without DNS:

- Users would have to remember numeric IP addresses
    
- Websites could not move servers easily
    
- Emails and applications would not know where to connect
    

DNS makes the internet usable for humans and manageable for systems.  
Everything that follows in DNS is simply different ways of storing and answering information about a domain.

### NS Record: Who Controls the Domain

**NS (Name Server)** records tell the internet **who is responsible for a domain**.

Think of them as the official office for a neighborhood.  
If anyone asks questions about your domain, the NS record tells them where to ask.

Important point:  
NS records define **authority**, not websites or emails.

---

### A Record: Where the Website Lives (IPv4)

**A (Address)** records connect a domain to an IPv4 address.

Example:  
[`example.com`](http://example.com/) `→ 93.184.216.34`

This is the core record that lets your browser reach a website.  
Name goes in, house address comes out.

---

### AAAA Record: Same Job, Newer Address (IPv6)

AAAA records do the same job as A records, but with **IPv6 addresses**.

- A → IPv4 (older)
    
- AAAA → IPv6 (newer)
    

If supported, browsers prefer AAAA.

---

### CNAME Record: One Name Follows Another

**CNAME** records point **one domain name to another domain name**, not to an IP.

Example:  
[`www.example.com`](http://www.example.com/) `→` [`example.com`](http://example.com/)

Useful when you want multiple names to lead to the same place without managing IPs everywhere.

Simple rule:

- A → IP address
    
- CNAME → another name
    

Never both for the same name.

---

### MX Record: Where Emails Go

**MX (Mail Exchange)** records decide **where emails for your domain should be delivered**.

When someone sends mail to [`you@example.com`](mailto:you@example.com), mail servers check the MX record.

Clear distinction:

- NS → who manages DNS
    
- MX → where emails are delivered
    

---

### TXT Record: Proof and Trust

**TXT** records store extra information.

They are mainly used for:

- Domain verification
    
- Email security
    
- Connecting services like GitHub or Hashnode
    

Think of them as small notes that help services trust your domain.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769444886266/d34e2bb1-6946-4a98-9053-7be749565085.png)
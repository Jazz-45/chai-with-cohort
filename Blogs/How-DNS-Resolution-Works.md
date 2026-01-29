
# How DNS Resolution Works

## Introduction

Whenever we write a [google.com](https://google.com/) on our search bar, we get a response from a google server hosted in a remote location. It actually uses the IP address and the PORT where the google server is hosted. It uses all the network elements discussed in our previous blog.

### Problem

Web browser only understand the IP address of the servers and interacts with them. As humans we cannot learn the IP address of many website. Instead of that we use the domain names of the websites, for example google.com. Let us say the IP address of it is 192.64.65.1 . So the question is how our browser get to know that what is the particular IP addressof an website?

### Solution

The solution is DNS (Domain Name Service). DNS is mapping of IP address and domain names. It’s something similar to a map datastructre and hence it is also known as Internet’s Phonebook. DNS does the heavy-lifting by memorizing domain names and their IPs.

## DNS

DNS (Domain Name Service) is a software that provides the address of a website whose name is typed in the search box of a browser. But this is not as simple as it looks. One might assume that DNS simply returns the IP of a website. But instead it only tells whom should you talk to next? It tells where you should ask next to get your domain name resolved.

## DNS Hierarchy

DNS have some hierachy starting from the root server represented by `.`. Root servers contains the address of all the TLD (Top-Level Domain) Servers such as `.com` `.net` `.org`. The TLD servers contains all the authoratative domain names with a specific top-level domain. Then this ADNS contains the address that we actually need. DNS Hierarchy is way to minimize our search of the IP address. It helps in reducing the search space and overhead.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769434846114/950ab02b-d6d7-47b5-b1d1-91e4bd0b12a1.png)

## DNS Resolution

Let’s See how actually resolution works with the example of `google.com`. Firstly the `.com` is resolved and the DNS directs you to the `.com` TLD server. We then resolve the `google` with the TLD server it directs us to Authoratative DNS server where google.com lives. This server finally gives the IP address of the website which we to again use to request to get the response.

To avoid these many resolution we a use a **Recursive DNS Resolver** which performs the resolution till it doesn’t gets the final IP address.

## DNS Lookup Process (Using [`google.com`](http://google.com/) as the Example)

1. A user enters [**google.com**](http://google.com/) into a web browser. The browser forwards this request to a **DNS recursive resolver**, typically operated by the user’s ISP or a public DNS provider.
    
2. The recursive resolver checks its cache. If no valid record is found, it initiates a query to a **DNS root nameserver**.
    
3. The root nameserver does not know the IP address of [**google.com**](http://google.com/), but it responds with the location of the appropriate **Top-Level Domain (TLD) nameserver**, in this case the **.com** TLD.
    
4. The recursive resolver then sends a query to the **.com TLD nameserver**.
    
5. The TLD nameserver responds with the address of the **authoritative nameserver** responsible for [**google.com**](http://google.com/).
    
6. The recursive resolver queries the authoritative nameserver for [**google.com**](http://google.com/).
    
7. The authoritative nameserver returns the **IP address** associated with [**google.com**](http://google.com/) to the recursive resolver.
    
8. The recursive resolver caches the result for future requests and sends the IP address back to the user’s browser.
    

---

## What Happens After DNS Resolution

9. Using the resolved IP address, the browser sends an **HTTP/HTTPS request** to the server hosting [**google.com**](http://google.com/).
    
10. The server processes the request and returns the webpage content, which the browser then renders for the user.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769434860940/abd07edb-3983-4d98-9dc0-99b6b9cc7914.png)

## What Is the `dig` Command and When Is It Used?

`dig` (Domain Information Groper) is a command-line tool used to query DNS servers directly. It is primarily used for **DNS troubleshooting, verification, and learning** how domain name resolution works by exposing raw DNS responses.

Example:

```bash
dig google.com
```

---

### `dig . NS` — Root Name Servers

```bash
dig . NS
```

Queries the DNS **root zone (**`.`) and returns the list of **root name servers**. These servers sit at the top of the DNS hierarchy and direct queries to the appropriate Top-Level Domain (TLD) servers.

---

### `dig com NS` — TLD Name Servers

```bash
dig com NS
```

Retrieves the **.com TLD name servers**. TLD servers manage domain delegation and point resolvers to the **authoritative name servers** of individual domains.

---

### `dig` [`google.com`](http://google.com/) `NS` — Authoritative Name Servers

```bash
dig google.com NS
```

Returns the **authoritative name servers** for [**google.com**](http://google.com/), which store and serve the actual DNS records for the domain.

---

### `dig` [`google.com`](http://google.com/) — Full DNS Resolution Flow

```bash
dig google.com
```

Performs a complete DNS lookup through a recursive resolver, ultimately returning the IP address for [**google.com**](http://google.com/). To observe the entire resolution path explicitly:

```bash
dig google.com +trace
```
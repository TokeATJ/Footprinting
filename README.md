# Footprinting

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/e4a58928-8af2-4494-bb9a-3c1767ee00e6" />


# 🕵️ Footprinting Lab Using Kali Linux
# Disclaimer

This repository contains educational examples created for cybersecurity training and portfolio demonstration purposes. Domain names, contact information, IP addresses, and ownership records have been modified and sanitized for public publication.

## Overview

This lab demonstrates the use of common reconnaissance and footprinting tools in Kali Linux to gather publicly available information about domains, DNS infrastructure, web servers, and hosting providers.

**Tools Used:**

* `dig`
* `nslookup`
* `whois`
* `dnsenum`
* Kali Linux

---

# Part I: Footprinting

## 1. Find Start of Authority (SOA) Information

### Objective

Identify the Start of Authority (SOA) information for the domain name `localhost`.

### Command Used

```bash
dig SOA localhost
```

### SOA Information

| Record Type         | Value                 |
| ------------------- | --------------------- |
| Primary Name Server | abc.test.com          |
| Responsible Party   | info.version-kali.com |

### Screenshot

![SOA Information](images/01-soa-information.png)

---

## 2. Gather Domain Ownership Information

### Objective

Identify ownership information associated with `www.example.test.com`.

### Command Used

```bash
whois example.test.com
```

### Results

| Field | Value                                             |
| ----- | ------------------------------------------------- |
| Owner | Peter Griffin                                     |
| Phone | +1 404-609-6576                                   |
| Email | [PG@example.test.com](mailto:PG@example.test.com) |

### Screenshot

![WHOIS Domain Information](images/02-domain-owner.png)

---

## 3. Identify Website Hosting Information

### Objective

Determine the web server IP address and hosting provider for `www.example.test.com`.

### Commands Used

```bash
dig www.example.test.com +short
```

```bash
nslookup www.example.test.com
```

```bash
whois 192.0.2.10
```

### Results

| Item                 | Value                                             |
| -------------------- | ------------------------------------------------- |
| Web Server IP        | 192.0.2.10                                        |
| Hosting Organization | Example Hosting Services                          |
| Technical Contact    | Peter Griffin                                     |
| Contact Email        | [PG@example.test.com](mailto:PG@example.test.com) |

### Screenshot

![Hosting Information](images/03-hosting-information.png)

---

## 4. Identify Technical Contact Information

### Objective

Determine the organization responsible for hosting the website and identify the technical contact.

### Command Used

```bash
whois 192.0.2.10
```

### Results

| Item              | Value                                             |
| ----------------- | ------------------------------------------------- |
| Organization      | Example Hosting Services                          |
| Technical Contact | Peter Griffin                                     |
| Email Address     | [PG@example.test.com](mailto:PG@example.test.com) |

### Screenshot

![Technical Contact Information](images/04-technical-contact.png)

---

## 5. Identify DNS Servers Used by Kali Linux

### Objective

Determine which DNS servers are configured on the Kali Linux virtual machine.

### Command Used

```bash
cat /etc/resolv.conf
```

### Results

| DNS Server  |
| ----------- |
| 75.75.75.75 |
| 75.75.76.76 |

### Screenshot

![DNS Server Configuration](images/05-dns-server.png)

---

## 6. Enumerate DNS Information Using dnsenum

### Objective

Perform DNS enumeration against `www.example.test.com`.

### Command Used

```bash
dnsenum www.example.test.com > results.txt
```

### Information Discovered

#### Host Address

```text
192.0.2.10
```

#### Name Servers

```text
ns1.example.test.com
ns2.example.test.com
```

#### Mail Servers

```text
mail.example.test.com
```

#### Additional Hosts

```text
ftp.example.test.com
dev.example.test.com
```

### Analysis

The `dnsenum` utility was used to enumerate DNS records associated with the target domain. The tool identified host records, mail servers, and authoritative name servers. Results were redirected to a file (`results.txt`) for documentation and review.

### Screenshot

![DNS Enumeration Results](images/06-dnsenum-results.png)

---

# Skills Demonstrated

* Footprinting
* Open Source Intelligence (OSINT)
* DNS Enumeration
* WHOIS Analysis
* Host Discovery
* Domain Reconnaissance
* Technical Contact Identification
* DNS Infrastructure Analysis
* Kali Linux Administration
* Network Reconnaissance

---


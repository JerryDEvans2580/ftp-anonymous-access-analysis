# FTP Anonymous Access Analysis

## Overview

This repository documents a practical lab exercise involving FTP service enumeration and anonymous access.

During enumeration, an FTP service allowing anonymous authentication was discovered. Two different approaches were used to retrieve files from the server.

The first approach involved automated mirroring without interactive login.  
The second approach involved direct anonymous authentication using the FTP client.

This repository focuses on methodology, observations, and lessons learned during the process.

---

## Service Enumeration

Initial scan: 
sudo nmap -sV -p21 -sC -A <target> 

Finding	Description

FTP banner	Service version was identified from banner
Anonymous login	FTP server allows anonymous authentication
System information	FTP system type information exposed
Network path	traceroute revealed network route
OS fingerprint	Nmap attempted OS identification

The most critical issue is anonymous FTP access.

---

## Initial Approach – Automated Mirroring

At first, the files were retrieved using a mirroring technique:
wget -m --no-passive ftp://anonymous:anonymous@ <TARGET>

Explanation:

- `-m` enables mirror mode
- `--no-passive` forces active FTP mode
- Credentials are provided directly in the URL

This successfully downloaded the available files from the FTP server.

However, this method was unnecessarily complex because anonymous authentication was already permitted.

---

## Correct Approach – Anonymous Login

After reviewing the enumeration results again, a simpler method was used.

Login via FTP client:

ftp <TARGET>
Name: anonymous
Password: anonymous

After authentication:

ls
get <filename>
This allowed direct access to the required file.

---

## Security Implication

Allowing anonymous FTP access may expose files if directory permissions are misconfigured.

Recommended mitigation:

- Disable anonymous FTP login unless necessary
- Restrict access to public directories
- Monitor FTP access logs

---

For additional notes see:
- methodology.md
- lessons-learned.md

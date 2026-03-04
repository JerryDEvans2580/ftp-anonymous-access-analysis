# Methodology

## Step 1 – Service Discovery

The first step was identifying open services using Nmap.


nmap -p21 -sV <TARGET>


The scan revealed an FTP service.

---

## Step 2 – Anonymous Access Verification

Using Nmap scripts:


nmap --script ftp-anon <TARGET>


Result:


Anonymous FTP login allowed (FTP code 230)


This confirmed that the server permitted anonymous authentication.

---

## Step 3 – File Retrieval

Two different techniques were used:

1. Automated mirroring using `wget`
2. Direct FTP authentication using `anonymous`

Both methods allowed file retrieval from the FTP service.

---

## Step 4 – Analysis

The automated mirroring approach worked but was not necessary.

Direct FTP login provided a simpler and clearer way to retrieve files.

This highlights the importance of reviewing enumeration results carefully before selecting tools.

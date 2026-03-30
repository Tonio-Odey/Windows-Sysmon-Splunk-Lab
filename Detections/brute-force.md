
# Brute Force Detection

## Description
Detects failed and successful login attempts on Windows using **EventCode 4625 (failed logon)** and **4624 (successful logon)**.

## Screenshot

![Brute Force Splunk Screenshot](../Screenshots/brute-force.png)

## Splunk Detection Query

```spl
index=winevents EventCode=4625 OR EventCode=4624

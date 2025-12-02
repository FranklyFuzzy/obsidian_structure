---
type:
  - resource
status:
  - reference
tags:
  - cheatsheet
created: 2025-11-30
updated: 2025-11-30
---
# Table of Contents
1. [[#Basic Scanning]]
2. [[#Port Scanning]]
3. [[#Service and Version Detection]]
4. [[#OS Detection]]
5. [[#Stealth Scanning]]
6. [[#Timing and Performance]]
7. [[#Output Formats]]
8. [[#Advanced Scanning]]
9. [[#Exclusions and Targets]]
10. [[#Help and Documentation]]


## Basic Scanning

- **Scan a single IP:**
    ```bash
    nmap <target-ip>
    ```

- **Scan a range of IPs:**
    ```bash
    nmap <start-ip>-<end-ip>
    ```

- **Scan multiple IPs:**
    ```bash
    nmap <ip1> <ip2> <ip3>
    ```

- **Scan an entire subnet:**
    ```bash
    nmap <subnet>/24
    ```

## Port Scanning

- **Scan specific ports:**
    ```bash
    nmap -p <port1>,<port2> <target>
    ```

- **Scan a range of ports:**
    ```bash
    nmap -p <start-port>-<end-port> <target>
    ```

- **Scan all 65535 ports:**
    ```bash
    nmap -p- <target>
    ```

- **Scan top 1000 ports (default):**
    ```bash
    nmap <target>
    ```

## Service and Version Detection

- **Detect services and versions:**
    ```bash
    nmap -sV <target>
    ```

- **Aggressive scan (includes service detection):**
    ```bash
    nmap -A <target>
    ```

## OS Detection

- **Detect operating system:**
    ```bash
    nmap -O <target>
    ```

- **Aggressive scan with OS detection:**
    ```bash
    nmap -A -O <target>
    ```

## Stealth Scanning

- **TCP SYN scan (default scan):**
    ```bash
    nmap -sS <target>
    ```

- **TCP Connect scan:**
    ```bash
    nmap -sT <target>
    ```

- **UDP scan:**
    ```bash
    nmap -sU <target>
    ```

## Timing and Performance

- **Set timing template (0-5):**
    ```bash
    nmap -T<template> <target>
    ```
    - **0**: Paranoid
    - **1**: Sneaky
    - **2**: Polite
    - **3**: Normal
    - **4**: Aggressive
    - **5**: Insane

- **Increase verbosity:**
    ```bash
    nmap -v <target>
    ```

- **Increase debugging:**
    ```bash
    nmap -d <target>
    ```

## Output Formats

- **Normal output:**
    ```bash
    nmap -oN output.txt <target>
    ```

- **XML output:**
    ```bash
    nmap -oX output.xml <target>
    ```

- **Grepable output:**
    ```bash
    nmap -oG output.grep <target>
    ```

- **JSON output:**
    ```bash
    nmap -oJ output.json <target>
    ```

## Advanced Scanning

- **Scan for specific script (NSE):**
    ```bash
    nmap --script <script-name> <target>
    ```

- **Run all default scripts:**
    ```bash
    nmap --script default <target>
    ```

- **Scan for vulnerabilities using scripts:**
    ```bash
    nmap --script vuln <target>
    ```

- **Detect open ports using a specific script:**
    ```bash
    nmap --script=<script-name> -p <port> <target>
    ```

## Exclusions and Targets

- **Exclude hosts:**
    ```bash
    nmap --exclude <ip1>,<ip2> <target>
    ```

- **Exclude a range of IPs:**
    ```bash
    nmap --exclude <start-ip>-<end-ip> <target>
    ```

- **Include specific hosts only:**
    ```bash
    nmap --include <ip1>,<ip2> <target>
    ```

## Miscellaneous

- **Show all hosts in a subnet:**
    ```bash
    nmap -sn <subnet>/24
    ```

- **Check host discovery only (no port scan):**
    ```bash
    nmap -sn <target>
    ```

- **Scan for hostnames:**
    ```bash
    nmap -sL <target>
    ```

- **Perform a ping scan:**
    ```bash
    nmap -sn <target>
    ```

- **Scan without DNS resolution:**
    ```bash
    nmap -n <target>
    ```

## Help and Documentation

- **Show help:**
    ```bash
    nmap -h
    ```

- **Show version:**
    ```bash
    nmap -V
    ```

- **Read the manual:**
    ```bash
    man nmap
    ```

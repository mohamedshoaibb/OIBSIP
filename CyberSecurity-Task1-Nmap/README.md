# OASIS INFOBYTE - Security Analyst

## Task 1: Basic Network Scanning with Nmap

### Objective
Scan a local machine/VM for open ports and services using Nmap and document the security findings.

### Target
Kali Linux Virtual Machine

Target IP: 10.0.2.15

### Tools Used
- Nmap 7.99
- Kali Linux
- Terminal

## Scans Performed

### 1. Basic Scan

Command:

nmap 10.0.2.15

Result:

The host was up. The default 1000 TCP ports were scanned and were filtered with no response. No open ports were identified.

### 2. Service and Version Detection

Command:

nmap -sV 10.0.2.15

Result:

The host was up. The scanned TCP ports were filtered and no open services were identified.

### 3. OS Detection

Command:

sudo nmap -O 10.0.2.15

Result:

The host was up. Nmap could not identify a specific operating system because too many fingerprints matched. Network distance was 0 hops.

## Security Analysis

No open ports were identified in the default 1000 TCP ports scanned on the Kali VM.

Filtered ports did not provide a response to Nmap probes. This reduces the visible attack surface for these ports.

## Ethical Considerations

This scan was performed only against my own local Kali Linux virtual machine for educational and authorized security testing.

Nmap should only be used against systems for which permission has been obtained.

## Evidence

The following evidence should be included with this task:

- Basic Nmap scan screenshot
- Service/version scan screenshot
- OS detection scan screenshot
- nmap_scan_results.txt

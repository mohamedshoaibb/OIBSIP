# Task 1 - Basic Network Scanning with Nmap

## Objective

Perform basic network scanning using Nmap to identify open ports, running services, and the operating system of an authorized local system.

## Tools Used

* Nmap 7.991
* Npcap 1.88
* Windows Command Prompt
* Windows 11

## Target

**Target:** 127.0.0.1 (Localhost)

The scan was performed against my own local computer for educational and authorized security testing.

## Scans Performed

### 1. Basic Network Scan

Command:

```bash
nmap 127.0.0.1
```

The scan identified three open TCP ports:

| Port     | State | Service      |
| -------- | ----- | ------------ |
| 135/tcp  | Open  | msrpc        |
| 445/tcp  | Open  | microsoft-ds |
| 5357/tcp | Open  | wsdapi       |

997 TCP ports were reported as closed.

### 2. Service and Version Detection

Command:

```bash
nmap -sV 127.0.0.1
```

Results:

| Port     | Service      | Version/Identification             |
| -------- | ------------ | ---------------------------------- |
| 135/tcp  | msrpc        | Microsoft Windows RPC              |
| 445/tcp  | microsoft-ds | Version not confidently identified |
| 5357/tcp | wsdapi       | Version not confidently identified |

Nmap identified the operating system as Windows.

### 3. Operating System Detection

Command:

```bash
nmap -O 127.0.0.1
```

Result:

* Device type: General purpose
* Operating system: Microsoft Windows 11
* OS details: Windows 11 24H2 - 25H2
* Network distance: 0 hops

## Security Risk Analysis

### Port 135 - Microsoft Windows RPC

Windows RPC is used for communication between Windows components and services.

**Potential risk:** If unnecessarily exposed to untrusted networks, RPC services can increase the attack surface.

**Recommendation:** Restrict unnecessary access using Windows Firewall and avoid exposing RPC services directly to untrusted networks.

### Port 445 - Microsoft-DS / SMB

Port 445 is commonly associated with Windows SMB services used for file and printer sharing.

**Potential risk:** SMB exposure can increase the attack surface, particularly when systems are improperly configured or unpatched.

**Recommendation:** Restrict SMB access to trusted networks and keep Windows security updates enabled.

### Port 5357 - WSDAPI

Port 5357 is associated with Web Services for Devices.

**Potential risk:** Unnecessary device-discovery services can increase the number of exposed services.

**Recommendation:** Disable unnecessary device-discovery features or restrict their network access when they are not required.

## Key Findings

1. Three TCP ports were open on the local system.
2. Port 135 was identified as Microsoft Windows RPC.
3. Ports 445 and 5357 were detected, but Nmap could not confidently determine their exact versions.
4. Nmap identified the operating system as Microsoft Windows 11.
5. The scan was performed only against the local machine (127.0.0.1).

## Ethical Considerations

This security assessment was performed only against a system that I own and am authorized to test.

Network scanning should only be performed with proper authorization. Scanning systems without permission may be illegal or disruptive.

## Conclusion

Nmap was successfully used to perform basic port scanning, service detection, and operating system detection on a local Windows system. The results provide an overview of the exposed services and can be used to identify services that may require further security review or restriction.


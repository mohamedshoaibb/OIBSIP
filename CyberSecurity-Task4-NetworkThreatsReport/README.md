# Task 4 – Network Threats Research Report

## Objective

To research common network security threats, understand how they affect systems and networks, and identify appropriate detection and mitigation techniques.

## Introduction

Network security is the practice of protecting computer networks, devices, applications, and data from unauthorized access, misuse, disruption, and attacks.

Network threats can target the confidentiality, integrity, and availability of information. Understanding common attack techniques helps security professionals identify risks and implement appropriate defensive controls.

## 1. Distributed Denial-of-Service (DDoS)

### Description

A Distributed Denial-of-Service (DDoS) attack attempts to make a service or network resource unavailable by overwhelming it with a large volume of traffic or requests.

Attackers commonly use many compromised devices, known as a botnet, to generate traffic toward the target.

### Impact

- Service disruption
- Slow network performance
- Application unavailability
- Loss of revenue
- Increased operational costs

### Detection

Security teams can monitor:

- Unusual traffic spikes
- Large numbers of requests
- Unexpected traffic sources
- Network bandwidth utilization
- Server resource usage

### Mitigation

- Rate limiting
- Traffic filtering
- Firewalls and intrusion prevention systems
- DDoS protection services
- Load balancing
- Network traffic monitoring

---

## 2. Man-in-the-Middle (MITM)

### Description

A Man-in-the-Middle attack occurs when an attacker positions themselves between two communicating systems and attempts to intercept or manipulate their communication.

For example, an attacker on an insecure network may attempt to intercept network traffic between a user and a server.

### Impact

- Credential theft
- Session hijacking
- Data interception
- Modification of communications
- Loss of confidentiality

### Detection

Possible indicators include:

- Unexpected certificate warnings
- Suspicious network devices
- Unusual ARP activity
- Unexpected changes in network routing

### Mitigation

- Use HTTPS and TLS
- Avoid untrusted networks when possible
- Use VPNs on untrusted networks
- Validate digital certificates
- Use secure authentication methods
- Implement network monitoring

---

## 3. DNS Attacks

### Description

The Domain Name System (DNS) translates domain names into IP addresses. Attackers can abuse DNS through techniques such as DNS spoofing, DNS cache poisoning, or DNS tunneling.

### Impact

- Users redirected to malicious websites
- Credential theft
- Malware distribution
- Data exfiltration
- Service disruption

### Detection

Security teams can monitor:

- Unusual DNS queries
- Unexpected DNS servers
- Large volumes of DNS traffic
- Suspicious domain names
- Abnormal DNS responses

### Mitigation

- Use secure DNS infrastructure
- Restrict unauthorized DNS servers
- Monitor DNS traffic
- Keep DNS software updated
- Use DNS security controls such as DNSSEC where appropriate

---

## 4. Malware

### Description

Malware is malicious software designed to disrupt systems, steal information, gain unauthorized access, or perform other harmful actions.

Common types include:

- Viruses
- Worms
- Trojans
- Ransomware
- Spyware
- Remote access malware

### Impact

- Data theft
- Data destruction
- Financial loss
- System disruption
- Unauthorized access

### Detection

Organizations can use:

- Antivirus and endpoint protection
- Security logs
- SIEM systems
- File integrity monitoring
- Network monitoring
- Behavioral analysis

### Mitigation

- Keep software updated
- Use endpoint security
- Avoid untrusted downloads
- Apply least privilege
- Maintain regular backups
- Train users to recognize suspicious activity

---

## 5. Network Sniffing

### Description

Network sniffing involves capturing and analyzing network traffic. Network administrators may use packet capture for legitimate troubleshooting, but attackers can abuse the technique to obtain sensitive information from improperly secured traffic.

### Impact

- Credential exposure
- Sensitive data interception
- Session information exposure
- Loss of confidentiality

### Detection

Network monitoring tools can help identify:

- Unexpected packet capture activity
- Suspicious devices
- Abnormal network interfaces
- Unusual network traffic patterns

### Mitigation

- Use encrypted protocols
- Avoid transmitting sensitive information over unencrypted connections
- Use HTTPS and TLS
- Secure wireless networks
- Monitor network infrastructure

---

## 6. Spoofing

### Description

Spoofing occurs when an attacker falsifies identifying information to appear as another system, device, user, or service.

Examples include:

- IP spoofing
- MAC spoofing
- ARP spoofing
- DNS spoofing
- Email spoofing

### Impact

- Unauthorized access
- Traffic interception
- Fraud
- Credential theft
- Network disruption

### Detection

Security teams can monitor:

- Unexpected IP or MAC address changes
- Duplicate addresses
- Abnormal ARP activity
- Suspicious authentication activity

### Mitigation

- Network segmentation
- Secure authentication
- ARP inspection where supported
- Access control
- Network monitoring
- Encryption

---

## 7. Phishing and Network-Based Social Engineering

### Description

Phishing uses deceptive messages or websites to trick users into revealing credentials, financial information, or other sensitive data.

Attackers may use email, messaging platforms, fake login pages, or malicious links.

### Impact

- Credential theft
- Malware infection
- Account compromise
- Financial loss
- Unauthorized access

### Detection

Users and security teams should look for:

- Suspicious links
- Unexpected attachments
- Urgent requests
- Fake login pages
- Sender address inconsistencies

### Mitigation

- Security awareness training
- Multi-factor authentication
- Email filtering
- Link and attachment scanning
- User reporting mechanisms

---

## 8. Network Vulnerability Exploitation

### Description

Attackers may exploit vulnerable software, outdated services, insecure configurations, or exposed network ports to gain unauthorized access.

### Impact

- Unauthorized system access
- Data theft
- Malware installation
- Privilege escalation
- Service disruption

### Detection

Security teams can use:

- Vulnerability scanners
- Network monitoring
- Intrusion detection systems
- Security logs
- Regular security assessments

### Mitigation

- Apply security patches
- Disable unnecessary services
- Use firewalls
- Apply least privilege
- Perform vulnerability assessments
- Harden network devices

---

# General Network Threat Detection

Organizations can use multiple security controls to detect network threats.

Important controls include:

1. Firewalls
2. Intrusion Detection Systems (IDS)
3. Intrusion Prevention Systems (IPS)
4. Security Information and Event Management (SIEM)
5. Network monitoring
6. Endpoint detection and response
7. Vulnerability scanning
8. Log analysis

A layered security approach provides better protection than relying on a single security control.

# General Prevention and Mitigation Strategy

A strong network security program should include:

- Regular patch management
- Strong authentication
- Multi-factor authentication
- Network segmentation
- Least-privilege access
- Secure configuration
- Encryption
- Firewall rules
- IDS/IPS monitoring
- Regular vulnerability assessments
- Security awareness training
- Incident response procedures
- Regular backups

# Security Analysis

Network threats can affect the confidentiality, integrity, and availability of information.

For example:

- **Confidentiality:** MITM attacks and network sniffing can expose sensitive information.
- **Integrity:** Spoofing and MITM attacks can allow communications to be manipulated.
- **Availability:** DDoS attacks can make services unavailable.

Therefore, organizations should use multiple layers of security controls and continuously monitor their networks.

# Conclusion

Network threats are a significant security risk for modern organizations. Attacks such as DDoS, MITM, DNS attacks, malware, sniffing, spoofing, phishing, and vulnerability exploitation can cause data loss, unauthorized access, financial damage, and service disruption.

Effective network security requires a combination of preventive, detective, and corrective controls. Regular patching, secure configuration, encryption, access control, network monitoring, user awareness, and incident response can significantly reduce the risk posed by network threats.

## Ethical Considerations

This report is intended for cybersecurity education and defensive security purposes. Security testing should only be performed on systems and networks that are owned by the tester or where explicit authorization has been provided.

## References

- CISA – Cybersecurity guidance and resources
- OWASP – Web and application security resources
- NIST – Cybersecurity Framework and security guidance
- MITRE ATT&CK – Adversary tactics and techniques

# Task 2 - UFW Firewall Configuration

## Objective

To configure and manage the Uncomplicated Firewall (UFW) on Kali Linux and control incoming network traffic.

## Environment

- Operating System: Kali Linux
- Firewall: UFW (Uncomplicated Firewall)
- Platform: Oracle VirtualBox

## Configuration Performed

The UFW firewall was enabled and configured with a default-deny policy for incoming connections.

The following services were allowed:

| Port | Protocol | Service | Action |
|------|----------|---------|--------|
| 22 | TCP | SSH | Allow |
| 80 | TCP | HTTP | Allow |
| 443 | TCP | HTTPS | Allow |

UFW also created the corresponding IPv6 rules automatically.

## Commands Used

### Install UFW

    sudo apt install ufw -y

### Enable the Firewall

    sudo ufw enable

### Check Firewall Status

    sudo ufw status verbose

### Allow SSH

    sudo ufw allow ssh

### Allow HTTP

    sudo ufw allow 80/tcp

### Allow HTTPS

    sudo ufw allow 443/tcp

### Enable Firewall Logging

    sudo ufw logging on

### Verify the Rules

    sudo ufw status numbered

## Final Firewall Status

The final UFW configuration was:

- Status: Active
- Logging: On (low)
- Default incoming: Deny
- Default outgoing: Allow
- Routed traffic: Disabled

Allowed incoming ports:

- 22/tcp - SSH
- 80/tcp - HTTP
- 443/tcp - HTTPS

IPv6 rules were also enabled for the same ports.

## Security Analysis

A default-deny incoming policy helps prevent unauthorized incoming network connections.

Only the required services were allowed:

- Port 22 (SSH): Used for secure remote administration.
- Port 80 (HTTP): Used for web traffic.
- Port 443 (HTTPS): Used for secure web traffic.

Firewall logging was enabled to help monitor firewall activity.

Allowing only required services helps reduce unnecessary network exposure.

## Evidence

A screenshot of the final UFW firewall configuration is included in this task folder.

The screenshot shows that the firewall is active and that SSH, HTTP, and HTTPS traffic are allowed.

## Conclusion

UFW was successfully installed, enabled, and configured on Kali Linux.

The firewall was configured to deny incoming connections by default while allowing the required SSH, HTTP, and HTTPS services. Firewall logging was also enabled.

This task demonstrates the basic configuration and management of a Linux firewall using UFW.

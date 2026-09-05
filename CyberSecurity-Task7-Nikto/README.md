# Task 7 – Nikto Web Server Scanning

## Objective

The objective of this task is to use Nikto to perform a security assessment of a web server in an authorized local lab environment, identify potential security issues, and document the findings and recommended mitigations.

## Environment

* Operating System: Kali Linux
* Security Tool: Nikto 2.6.0
* Web Server: nginx/1.30.1
* Target: DVWA
* Target Address: 127.0.0.1
* Target Port: 42001
* Environment: Local VirtualBox laboratory

## Ethical Considerations

The scan was performed only against a locally hosted DVWA instance running on the user's own Kali Linux virtual machine.

No external or production systems were scanned.

## Scan Command

The following command was used:

```bash
nikto -h http://127.0.0.1:42001
```

The scan was performed against the local DVWA web server.

## Scan Results

Nikto completed the scan successfully.

### Summary

* Target IP: 127.0.0.1
* Target Port: 42001
* Web Server: nginx/1.30.1
* Requests: 8191
* Errors: 0
* Reported Items: 8

## Findings

### 1. Missing X-Content-Type-Options Header

Nikto reported that the `X-Content-Type-Options` header was not set.

This security header helps prevent browsers from interpreting content as a different MIME type than declared.

### Risk

Missing this header can increase exposure to MIME-type sniffing-related attacks.

### Recommendation

Configure the web server to send:

```text
X-Content-Type-Options: nosniff
```

## 2. Missing Strict-Transport-Security Header

The `Strict-Transport-Security` header was not detected.

### Risk

For HTTPS deployments, the absence of HSTS can make it easier for attackers to influence users into making insecure HTTP connections.

### Recommendation

For websites that properly support HTTPS, configure an appropriate HSTS policy.

## 3. Missing Permissions-Policy Header

Nikto reported that the `Permissions-Policy` header was missing.

### Risk

This header can be used to control access to certain browser features and reduce unnecessary browser capabilities.

### Recommendation

Configure a suitable `Permissions-Policy` according to the application's requirements.

## 4. Missing Content-Security-Policy Header

Nikto reported that the `Content-Security-Policy` header was missing.

### Risk

A properly designed CSP can reduce the impact of certain client-side attacks, including some forms of cross-site scripting.

### Recommendation

Implement a restrictive Content Security Policy appropriate for the application.

## 5. Missing Referrer-Policy Header

Nikto reported that the `Referrer-Policy` header was missing.

### Risk

Without an appropriate policy, browsers may send more referrer information than necessary when navigating between resources.

### Recommendation

Configure a suitable Referrer-Policy based on the application's privacy and security requirements.

## 6. Login Page Detected

Nikto identified:

```text
/login.php
```

as an admin login page or login section.

### Risk

Login pages are common targets for credential attacks, password guessing, and other authentication attacks.

### Recommendation

Protect authentication endpoints with:

* Strong passwords.
* Multi-factor authentication where supported.
* Rate limiting.
* Account lockout or throttling controls.
* Secure session management.
* Monitoring and logging.

## 7. X-Frame-Options Observation

Nikto reported that the `X-Frame-Options` header is deprecated in favor of the `Content-Security-Policy` `frame-ancestors` directive.

### Risk

Improper framing protection can increase exposure to clickjacking attacks.

### Recommendation

Use an appropriate Content Security Policy with the `frame-ancestors` directive for modern protection.

## 8. Additional Content-Type Header Finding

Nikto again identified that the `X-Content-Type-Options` header was not set and noted that this could allow browsers to render content differently from the declared MIME type.

### Recommendation

Configure:

```text
X-Content-Type-Options: nosniff
```

and verify that the web server returns the header correctly.

## Security Analysis

The Nikto scan identified several web security hardening opportunities in the local DVWA environment.

The most important findings were the missing security headers and the exposed login endpoint.

Security headers provide an additional layer of browser-side protection, while authentication endpoints should be carefully protected against unauthorized access and automated attacks.

Because DVWA is intentionally designed as a vulnerable web application for security training, some findings are expected. The purpose of this assessment was to practice identifying and documenting these issues in an authorized environment.

## Recommended Mitigation Strategy

The following actions are recommended for a production web application:

1. Configure appropriate security headers.
2. Use HTTPS and configure HSTS where appropriate.
3. Implement a suitable Content Security Policy.
4. Protect authentication endpoints.
5. Use strong authentication controls.
6. Apply rate limiting to login endpoints.
7. Monitor authentication activity.
8. Keep the web server and application updated.
9. Regularly perform vulnerability assessments.
10. Review security configuration after changes.

## Evidence

The complete Nikto output is stored in:

```text
nikto_scan_results.txt
```

The file contains the scan results generated against the local DVWA server.

## Conclusion

Nikto successfully scanned the locally hosted DVWA web server and identified eight reported security items.

The assessment demonstrated how automated web-server scanning can identify missing security headers, exposed authentication pages, and other configuration issues.

The findings should be reviewed and remediated according to the risk and requirements of the environment. In this lab, the results are intended for cybersecurity education and practice.

## References

* Nikto Web Server Scanner documentation.
* OWASP Web Security resources.
* MDN Web Docs – HTTP Security Headers.
* National Institute of Standards and Technology (NIST) cybersecurity guidance.

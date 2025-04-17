# Security-Incident-Investigation-with-ELK-Stack

I performed a security incident analysis using the ELK Stack (Elasticsearch, Logstash, Kibana) to investigate real-world attack scenarios from a provided dataset. This investigation mapped the detected threats to the Lockheed Martin Cyber Kill Chain and the MITRE ATT&CK Framework to gain insights into attacker tactics and techniques.

Key Findings: Identified Attacks

* Distributed Denial of Service (DDoS) Attack: A significant surge in ICMP & HTTP requests caused service disruptions, peaking on August 31, 2021, and September 30, 2021.
* SSH Brute Force Attack: Over 19,500 failed login attempts targeted the root user, originating from malicious IPs primarily based in Jiangsu, China (Chinanet ISP).
* Credential Stuffing Attack: Attackers attempted unauthorized logins using previously exposed credentials (e.g., admin, johndoe123).
* Malicious File Upload (Remote Code Execution - RCE): Attackers uploaded PHP files (index.php) via /documents/upload/index.php, enabling remote code execution.

ELK Stack for Log Analysis & Detection

* Filebeat, Packetbeat, Auditbeat: Used to capture logs related to network traffic, authentication events, and system activity.
* Kibana: Enabled log visualization, filtering failed login attempts, HTTP request patterns, and suspicious file uploads.
* Elasticsearch Queries: Utilized to detect attack patterns, including correlating network traffic spikes and authentication failures over time.

Recommendations & Mitigation

* DDoS Protection: Implement rate limiting and use cloud-based filtering (Cloudflare, AWS Shield).
* SSH Hardening: Enforce Multi-Factor Authentication (MFA), Fail2Ban, and IP whitelisting to mitigate brute-force attacks.
* Credential Security: Adopt strong password policies and monitor for breached credentials.
* Secure File Uploads: Restrict the upload of executable files and enforce MIME type validation.
* Log Monitoring & Alerting: Automate threat detection by setting up ELK-based SIEM rules.

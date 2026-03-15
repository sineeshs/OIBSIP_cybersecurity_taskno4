# Common Network Security Threats and Countermeasures
### Report Submitted by Sineesh S
---

## Introduction
In our increasingly interconnected world, network security is a foundational requirement for any digital infrastructure. A network security threat is any malicious attempt to breach, disrupt, or gain unauthorized access to a computer network. This report examines six prevalent network security threats: **Denial of Service (DoS) attacks**, **Man-in-the-Middle (MITM) attacks**, **Spoofing**, **Malware & Ransomware**, **Insider Threats**, and **Advanced Persistent Threats (APTs)**. It details their mechanisms, impacts, modern real-world examples, and effective mitigation strategies.

---

## 1. Denial of Service (DoS) and Distributed Denial of Service (DDoS) Attacks

### How It Works
A Denial of Service (DoS) attack aims to shut down a machine or network, making it inaccessible to its intended users. Attackers achieve this by flooding the target with traffic or sending it information that triggers a crash. In a **Distributed Denial of Service (DDoS)** attack, the incoming traffic flooding the victim originates from many different sources (often a botnet of compromised devices).

### Impact
* **Service Unavailability:** Legitimate users cannot access websites, applications, or network resources.
* **Financial Loss:** E-commerce sites and service providers lose revenue for every minute of downtime.
* **Reputational Damage:** Prolonged outages degrade customer trust.

### Recent Example
**The 2025 Aisuru Botnet Record-Breaking Attacks:** In late 2025, a massive IoT botnet known as "Aisuru" (powered by hundreds of thousands of compromised home routers and cameras) launched some of the largest DDoS attacks in history, hitting cloud infrastructure providers with devastating UDP floods exceeding 22 Terabits per second (Tbps). 

### Mitigation Strategies
* **Traffic Analysis and Rate Limiting:** Establish baselines for normal network traffic and limit the number of requests a server will accept.
* **DDoS Protection Services:** Utilize cloud-based scrubbing centers (e.g., Cloudflare, Akamai) that filter malicious traffic.

---

## 2. Man-in-the-Middle (MITM) Attacks

### How It Works
In a MITM attack, the perpetrator secretly intercepts and potentially alters the communication between two parties. The attacker acts as an invisible proxy, eavesdropping on the traffic or injecting malicious data. Common vectors include rogue Wi-Fi hotspots, ARP spoofing, and Adversary-in-the-Middle (AiTM) phishing proxies.

### Impact
* **Data Theft:** Interception of sensitive information such as login credentials and proprietary business data.
* **Session Hijacking (MFA Bypass):** Attackers can steal active session cookies to bypass Multi-Factor Authentication (MFA).

### Recent Example
**The 2024 Australian "Evil Twin" Airport Arrest:** In July 2024, Australian authorities arrested an individual who set up "evil twin" rogue Wi-Fi hotspots at airports. These fake networks mimicked legitimate free public Wi-Fi to intercept traveler traffic and harvest credentials.

### Mitigation Strategies
* **End-to-End Encryption (TLS/HTTPS):** Ensure all web traffic is encrypted and use HTTP Strict Transport Security (HSTS).
* **Virtual Private Networks (VPNs):** Use VPNs on public networks to create a secure, encrypted tunnel.
* **FIDO2 / Phishing-Resistant MFA:** Implement hardware security keys to neutralize AiTM proxy attacks.

---

## 3. Spoofing Attacks

### How It Works
Spoofing occurs when a malicious party impersonates a known or trusted device, user, or network. Modern spoofing extends beyond network protocols (like IP or DNS spoofing) into highly convincing social engineering, such as forging email addresses or using AI for biometric deepfakes.

### Impact
* **Bypassing Access Controls:** IP spoofing can bypass IP-based authentication networks.
* **Massive Financial Fraud:** Business Email Compromise (BEC) and identity spoofing trick employees into authorizing massive wire transfers.

### Recent Example
**The 2024 Arup $25 Million Deepfake Attack:** Arup, a multinational engineering firm, suffered a $25 million loss when an employee authorized wire transfers after a video conference call. Every other participant on the call, including the "CFO," was a real-time AI-generated deepfake spoofing actual executives.

### Mitigation Strategies
* **Packet Filtering:** Implement ingress and egress filtering on routers to block suspicious IP addresses.
* **Email Authentication Protocols:** Implement SPF, DKIM, and DMARC to prevent email spoofing.
* **Strict Verification Workflows:** Require out-of-band verification for high-risk actions to combat AI deepfake spoofing.

---

## 4. Malware and Ransomware

### How It Works
Malware (malicious software) is designed to infiltrate, damage, or disable networks and endpoints. Ransomware is a specific, highly destructive subset that encrypts an organization's files, databases, or entire systems. The attackers then demand a ransom (usually in cryptocurrency) in exchange for the decryption key, often employing "double extortion" by threatening to leak sensitive data if the ransom isn't paid.



### Impact
* **Complete Operational Paralysis:** Critical systems are locked down, halting day-to-day operations.
* **Data Loss and Privacy Breaches:** Sensitive records (such as student data in educational institutions or patient data in healthcare) are stolen and potentially published on the dark web.
* **Massive Financial Damage:** Costs include the ransom itself, lost operational time, and extensive recovery efforts.

**The 2024 Change Healthcare Ransomware Attack:** In early 2024, the ALPHV/Blackcat ransomware cartel breached Change Healthcare (a subsidiary of UnitedHealth Group). The attack crippled billing and pharmacy operations across the United States for weeks, highlighting the devastating cascading effects of ransomware on critical infrastructure. The company reportedly paid a $22 million ransom to restore systems.

### Mitigation Strategies
* **Robust Offline Backups:** Maintain frequent, immutable, and offline backups (following the 3-2-1 backup rule) to ensure data can be restored without paying the ransom.
* **Endpoint Detection and Response (EDR):** Deploy advanced EDR agents on all workstations and servers to detect malicious processes before encryption begins.
* **Centralized Log Management:** IT administrators should aggregate logs from firewalls, servers, and endpoints to detect the early stages of a malware infection.

---

## 5. Insider Threats

### How It Works
An insider threat is a security risk that originates from within the targeted organization. This could be a current or former employee, a contractor, or a business partner who has legitimate access to the network. Insider threats can be **malicious** (stealing data for financial gain or revenge) or **accidental** (an employee unknowingly clicking a phishing link or misconfiguring a database).



### Impact
* **Data Exfiltration:** Insiders know exactly where the most valuable data is stored, making it easier to steal.
* **Sabotage:** Disgruntled IT staff or highly privileged users can delete configurations, wipe servers, or intentionally introduce vulnerabilities.
* **Compliance Violations:** Mishandling of internal records can result in severe legal and regulatory penalties.

**The 2024 Tesla Insider Breach:** Tesla was forced to notify over 75,000 employees that their personal data (including names, addresses, and Social Security numbers) had been compromised. An investigation revealed that the breach was not the result of an external hack, but rather two former employees who misappropriated the information and shared it with a foreign media outlet.

### Mitigation Strategies
* **Principle of Least Privilege (PoLP):** Ensure users only have the bare minimum network access required to perform their specific job functions.
* **Strict Offboarding Procedures:** Immediately revoke all network access, VPN profiles, and physical keys the moment an employee leaves an institution.
* **User and Entity Behavior Analytics (UEBA):** Monitor networks for anomalous behavior, such as a user suddenly downloading gigabytes of sensitive files at 2:00 AM.

---

## 6. Advanced Persistent Threats (APTs)

### How It Works
An APT is a prolonged, highly sophisticated, and targeted cyberattack. Instead of a quick "smash and grab," the intruders (often state-sponsored hacking groups) establish a foothold in the network and remain undetected for months or even years. They move laterally across the network, escalating privileges and establishing backdoors to maintain access even if one point of entry is discovered.



### Impact
* **Long-Term Espionage:** Continuous surveillance of an organization's communications and strategic plans.
* **Deep Network Compromise:** The entire domain environment may become compromised, requiring a complete network rebuild to ensure the threat is eradicated.
* **Intellectual Property Theft:** Slow, stealthy siphoning of proprietary research, source code, or national security secrets.

**The 2024 Microsoft Midnight Blizzard Attack:** In January 2024, Microsoft disclosed that a Russian state-sponsored APT group known as "Midnight Blizzard" (or Nobelium) had breached its corporate network. The attackers used a password spray attack to compromise a legacy, non-MFA test account. From there, they moved laterally and accessed the email accounts of senior leadership and cybersecurity teams for months, attempting to discover exactly what Microsoft knew about their hacking operations.

### Mitigation Strategies
* **Security Information and Event Management (SIEM):** Deploying a robust SIEM platform (such as an open-source solution like Wazuh or a commercial equivalent) in a Security Operations Center (SOC) is critical. A SIEM aggregates and correlates events across the entire network, allowing SOC analysts to hunt for the subtle, low-and-slow indicators of an APT.
* **Network Segmentation:** Divide the network into secure zones to prevent an attacker who breaches one area from easily moving laterally to critical servers.
* **Proactive Threat Hunting:** Security teams must actively search through network data and logs for hidden adversaries, rather than just waiting for automated alerts to trigger.

---

## Threat Summary & General Preventive Measures

| Threat Type | Primary Vector | Core Objective | Key Defense Mechanism |
| :--- | :--- | :--- | :--- |
| **DoS/DDoS** | Traffic flooding (IoT Botnets) | Disrupt availability | Rate limiting, Cloud scrubbing |
| **MITM** | Interception (Rogue Wi-Fi, Proxies) | Steal session data/MFA bypass | End-to-end encryption, VPNs, FIDO2 |
| **Spoofing** | Impersonation (IP, Email, Deepfakes)| Bypass trust/auth controls | Packet filtering, DMARC, Out-of-band verification |
| **Ransomware** | Malicious payloads | Encrypt data for extortion | Immutable backups, EDR, network monitoring |
| **Insider Threat** | Legitimate privileged access | Data theft, accidental exposure | Principle of Least Privilege, UEBA |
| **APT** | Stealthy, multi-stage infiltration | Long-term espionage / IP theft | SIEM deployment, Threat hunting, Segmentation |

### General Network Security Best Practices
1.  **Zero Trust Architecture:** Never trust any user or device implicitly, whether inside or outside the network perimeter. Always verify.
2.  **Continuous Monitoring & SOC Integration:** Utilizing SIEM tools allows IT teams to detect anomalies and correlate security events in real time.
3.  **Employee Training:** Human error remains the weakest link. Regular training on recognizing modern phishing, AiTM proxies, and AI deepfake communications is critical for all staff members.
4.  **Vulnerability Management:** Regularly patch and update all systems, routers, and firewalls to close known exploits.

## Conclusion
Network security is an ongoing arms race between malicious actors and IT professionals. Threats continue to evolve—from simple packet floods and plaintext interception to massive 22-Tbps botnets, state-sponsored APTs, and real-time AI video deepfakes. Mitigating these modern threats requires a defense-in-depth approach: combining robust architectural choices (like Zero Trust and micro-segmentation), continuous monitoring through a modern SOC, rigorous encryption standards, phishing-resistant authentication, and vigilant human oversight.

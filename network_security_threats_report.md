# Research Report: Common Network Security Threats and Countermeasures

## 1. Introduction
In our increasingly interconnected world, network security is a foundational requirement for any digital infrastructure. A network security threat is any malicious attempt to breach, disrupt, or gain unauthorized access to a computer network. This report examines three prevalent network security threats: **Denial of Service (DoS) attacks**, **Man-in-the-Middle (MITM) attacks**, and **Spoofing**. It details their mechanisms, impacts, modern real-world examples, and effective mitigation strategies.

---

## 2. Denial of Service (DoS) and Distributed Denial of Service (DDoS) Attacks

### How It Works
A Denial of Service (DoS) attack aims to shut down a machine or network, making it inaccessible to its intended users. Attackers achieve this by flooding the target with traffic or sending it information that triggers a crash. In a **Distributed Denial of Service (DDoS)** attack, the incoming traffic flooding the victim originates from many different sources (often a botnet of compromised devices), making it impossible to stop the attack simply by blocking a single IP address.

### Impact
* **Service Unavailability:** Legitimate users cannot access websites, applications, or network resources.
* **Financial Loss:** E-commerce sites and service providers lose revenue for every minute of downtime.
* **Reputational Damage:** Prolonged outages degrade customer trust.
* **Smokescreen Effect:** Attackers sometimes use DDoS attacks to distract security teams while executing data breaches elsewhere in the network.

### Recent Real-World Example
**The 2025 Aisuru Botnet Record-Breaking Attacks:** In late 2025, a massive IoT botnet known as "Aisuru" (powered by hundreds of thousands of compromised home routers and cameras) launched some of the largest DDoS attacks in history. In September and October 2025, Aisuru targeted cloud infrastructure providers with devastating UDP floods. It hit Microsoft Azure with a 15.72 Terabits per second (Tbps) attack and prompted Cloudflare to mitigate an unprecedented 22.2 Tbps volumetric attack. 

### Mitigation Strategies
* **Traffic Analysis and Rate Limiting:** Establish baselines for normal network traffic and limit the number of requests a server will accept over a specific time window.
* **DDoS Protection Services:** Utilize cloud-based scrubbing centers (e.g., Cloudflare, Akamai, AWS Shield) that filter malicious traffic before it reaches your infrastructure.
* **Anycast Network Routing:** Scatter incoming traffic across a network of distributed servers, making it harder for an attacker to overwhelm a single location.

---

## 3. Man-in-the-Middle (MITM) Attacks

### How It Works
In a MITM attack, the perpetrator secretly intercepts and potentially alters the communication between two parties who believe they are communicating directly with each other. The attacker acts as an invisible proxy, eavesdropping on the traffic or injecting malicious data. Common vectors include rogue Wi-Fi hotspots, ARP spoofing, and Adversary-in-the-Middle (AiTM) phishing proxies.

### Impact
* **Data Theft:** Interception of sensitive information such as login credentials, credit card numbers, and proprietary business data.
* **Session Hijacking (MFA Bypass):** Attackers can steal active session cookies to impersonate a user and bypass Multi-Factor Authentication (MFA).
* **Data Manipulation:** Attackers can alter communication, such as changing the destination account number in a wire transfer request.

### Recent Real-World Example
**The 2024 Australian "Evil Twin" Airport Arrest:** In July 2024, Australian authorities arrested an individual operating a classic physical MITM attack. The attacker set up "evil twin" rogue Wi-Fi hotspots at airports and on domestic flights. These fake networks mimicked legitimate free public Wi-Fi. When travelers connected, the attacker intercepted their traffic and redirected them to spoofed login pages, successfully harvesting the credentials and session data of unsuspecting victims in transit.

### Mitigation Strategies
* **End-to-End Encryption (TLS/HTTPS):** Ensure all web traffic is encrypted. Use HTTP Strict Transport Security (HSTS) to force browsers to interact with your site only over HTTPS.
* **Virtual Private Networks (VPNs):** Use VPNs, especially on public Wi-Fi networks, to create a secure, encrypted tunnel for data transmission.
* **FIDO2 / Phishing-Resistant MFA:** Implement hardware security keys (like YubiKeys) or passkeys, which tie the authentication session to the specific legitimate domain, neutralizing AiTM proxy attacks.

---

## 4. Spoofing Attacks

### How It Works
Spoofing occurs when a malicious party impersonates a known or trusted device, user, or network to gain access to systems, steal data, or distribute malware. Modern spoofing extends beyond network protocols into highly convincing social engineering. Types of spoofing include:
* **IP/DNS Spoofing:** Altering source IP addresses or DNS records to impersonate trusted networks or divert traffic.
* **Email Spoofing:** Forging the "From" address of an email to make it appear as though it comes from a legitimate sender.
* **Deepfake/Biometric Spoofing:** Using AI to perfectly mimic the voice and visual appearance of a trusted individual.

### Impact
* **Bypassing Access Controls:** IP spoofing can allow attackers to bypass IP-based authentication networks.
* **Massive Financial Fraud:** Highly targeted Business Email Compromise (BEC) and identity spoofing trick employees into authorizing massive wire transfers.
* **Malware Distribution:** Email and DNS spoofing trick users into downloading malware or surrendering credentials.

### Recent Real-World Example
**The 2024 Arup $25 Million Deepfake Attack:** In early 2024, Arup, a multinational engineering firm, suffered a massive $25 million loss due to advanced AI spoofing. A finance employee in the Hong Kong office received a spoofed email from the "CFO" requesting a confidential transaction. To verify the request, the employee joined a live video conference. The call appeared to feature the CFO and several other familiar executives—but every other participant on the call was a real-time, AI-generated deepfake. Convinced by the spoofed video and audio, the employee authorized 15 wire transfers. 

### Mitigation Strategies
* **Packet Filtering:** Implement ingress and egress filtering on routers to block packets with source IP addresses that do not match the expected origin network.
* **Email Authentication Protocols:** Implement SPF (Sender Policy Framework), DKIM (DomainKeys Identified Mail), and DMARC to verify the sender's identity and prevent email spoofing.
* **Strict Verification Workflows:** For high-risk actions like wire transfers, require multi-person authorization and out-of-band verification (e.g., physically calling the person on a known internal phone number) to combat AI deepfake spoofing.

---

## 5. Threat Summary & General Preventive Measures

| Threat Type | Primary Vector | Core Objective | Key Defense Mechanism |
| :--- | :--- | :--- | :--- |
| **DoS/DDoS** | Traffic flooding (IoT Botnets) | Disrupt availability | Rate limiting, Cloud scrubbing |
| **MITM** | Interception (Rogue Wi-Fi, Proxies) | Steal session data/MFA bypass | End-to-end encryption, VPNs, FIDO2 MFA |
| **Spoofing** | Impersonation (IP, Email, Deepfakes)| Bypass trust/auth controls | Packet filtering, DMARC, Out-of-band verification |

### General Network Security Best Practices
1.  **Network Segmentation:** Divide the network into smaller, isolated segments to contain potential breaches.
2.  **Zero Trust Architecture:** Never trust any user or device implicitly, whether inside or outside the network perimeter. Always verify.
3.  **Continuous Monitoring:** Deploy Intrusion Detection and Prevention Systems (IDS/IPS) and Security Information and Event Management (SIEM) tools to detect anomalies in real time.
4.  **Employee Training:** Human error remains the weakest link. Regular training on recognizing modern phishing, AiTM proxies, and AI deepfake communications is critical.

## 6. Conclusion
Network security is an ongoing arms race between malicious actors and cybersecurity professionals. DoS, MITM, and spoofing attacks continue to evolve—from simple packet floods and plaintext interception to massive 22-Tbps botnets and real-time AI video deepfakes. Mitigating these modern threats requires a defense-in-depth approach: combining robust architectural choices (like Anycast and Zero Trust), rigorous encryption standards, phishing-resistant authentication protocols, and continuous network monitoring.

## 📌 What is Malware?

- **Malicious software** (malware) is one of the most common threats to endpoints.
    
- It may:
    
    - Spread autonomously across a network.
        
    - Arrive when a user clicks a malicious link or installs unsafe software.
        
- Once installed, malware can:
    
    - Gain control of system resources.
        
    - Steal sensitive information.
        

---

## 📌 Antimalware Protection Mechanisms

Antimalware software typically uses two detection techniques:

### 1️⃣ **Signature Detection**

- Relies on a **database of known malware patterns**.
    
- Scans files and memory for known malicious signatures.
    
- If detected, the software:
    
    - Removes or quarantines the malware.
        
- ⚠️ **Important:**  
    Virus definition files must be updated **frequently** to stay current with new threats.
    

---

### 2️⃣ **Heuristic Detection**

- Does **not** depend on known patterns.
    
- Models **normal system activity** and detects anomalies — behavior that deviates from the expected pattern.
    
- Useful for identifying **new or unknown malware**.


## 📌 Data Loss Prevention (DLP)

DLP solutions help organizations enforce **information handling policies** to prevent **data loss** and **theft**.

### Environments:

- 🖥 **Host-Based DLP**
    
    - Uses software agents on individual systems to:
        
        - Search for sensitive information (e.g., SSNs, credit card numbers) stored on the device.
            
        - Secure or remove sensitive data proactively.
            
        - Monitor system configuration & user actions.
            
        - Block risky actions (e.g., access to USB drives).
            
- 🌐 **Network-Based DLP**
    
    - Monitors outbound network traffic for unencrypted sensitive information.
        
    - Actions:
        
        - Block unauthorized transmissions.
            
        - Apply automatic encryption (common in email DLP systems).
            

---

### Detection Mechanisms:

- 🔷 **Pattern Matching**
    
    - Detects specific formats (e.g., SSNs, credit card numbers).
        
    - Looks for sensitive keywords (e.g., _Top Secret_, _Confidential_).
        
- 🔷 **Watermarking**
    
    - Tags sensitive documents with electronic markers.
        
    - Monitors systems & networks for unencrypted content containing these tags.
        

---

## 📌 Change & Configuration Management

### Configuration Management

- Tracks **endpoint settings** and **installed software**.
    
- Maintains documentation about system configurations, including diagrams for troubleshooting and investigations.
    

### Change Management

- Formal process for:
    
    - Identifying, requesting, approving, and implementing changes.
        
- Ensures unauthorized changes are detected and controlled.
    

---

### Key Concepts:

- 📋 **Baselining**
    
    - Snapshot of a system or application at a point in time.
        
    - Used to compare against current state to detect unauthorized changes.
        
- 🔢 **Version Control**
    
    - Assigns version numbers to software/scripts to track changes and identify releases.
        
- 📐 **Artifacts & Diagrams**
    
    - Visual and documented representations of configurations.
        
    - Help security professionals understand and troubleshoot systems quickly.


## 📌 What is System Hardening?

System hardening is the process of reviewing and adjusting the **default settings** of an operating system or application to remove unnecessary components and improve security.  
✅ Goal: Reduce the **attack surface** by minimizing what is installed, exposed, or enabled.

---

## 📌 Key Tasks in System Hardening

### 1️⃣ **Remove Unnecessary Components**

- Uninstall unneeded software & OS components.
    
- Configure the system for the **least functionality** required for its role.
    
- Fewer installed components = fewer opportunities for attackers.
    

---

### 2️⃣ **Lock Down Host Firewall**

- Only allow access to specific **ports & services** intended for use by authorized systems.
    
- Block everything else by default.
    

---

### 3️⃣ **Disable Default Accounts & Passwords**

- Many OS and applications come with **default accounts** and **passwords**.
    
- These are often known to attackers and are vulnerable to brute-force attacks.
    
- Disable or change them immediately.
    

---

### 4️⃣ **Verify System Configurations Against Best Practices**

- Check that configurations align with security standards and minimum requirements.
    
    - 🔷 On **Windows**: Modify registry settings as needed.
        
    - 🔷 On **Linux**: Edit configuration files to harden the system

## 📌 VLAN Security

### Best Practices for VLAN Implementation:

- 🔷 **VLAN Pruning**
    
    - Switches use **VLAN trunking** to carry multiple VLANs between switches.
        
    - VLAN pruning applies **least privilege** by only trunking VLANs that are actually needed on each switch.
        
    - Example:
        
        - Sales VLAN is only needed in the sales building — do **not** trunk it to other buildings.
            
    - Benefits:
        
        - Reduces attack surface if a switch is compromised.
            
        - Requires more administrative effort but improves security.
            
- 🔷 **Blocking VLAN Hopping**
    
    - Attackers may attempt to move from their VLAN to another (VLAN hopping), often by pretending to be a switch.
        
    - Countermeasures:
        
        - Disable automatic VLAN trunking negotiation.
            
        - Only trunk VLANs explicitly authorized by administrators.
            
        - Deny unauthorized VLAN trunk requests.
            

---

## 📌 Port Security

Port security protects the **physical switch ports** against unauthorized devices being connected.

### How it works:

- Limits the **MAC addresses** allowed on each switch port.
    
- Prevents attackers from unplugging an authorized device and connecting a rogue device.
    

### Port Security Modes:

- 🔷 **Static Mode**
    
    - Administrator manually configures each allowed MAC address on every port.
        
    - Most secure but very time-consuming.
        
- 🔷 **Dynamic / Sticky Mode**
    
    - Switch learns (memorizes) the first MAC address seen on the port and restricts access to that MAC.
        
    - Faster and easier to configure.
        
    - Risky if there are unused but active ports — attacker could connect first and claim the port.



## 📌 VPN Protocols

### 🛡 Traditional VPN Protocols:

- **IPsec (Internet Protocol Security)**
    
    - Used for creating encrypted tunnels.
        
    - Often chosen for **site-to-site (static) VPNs**.
        
    - Provides strong security at the network layer.
        
    - Difficult to configure and may be blocked by firewalls.
        
- **L2TP (Layer 2 Tunneling Protocol)**
    
    - Works at the **Data Link layer**.
        
    - Often combined with IPsec for secure transport.
        
    - Also robust but has similar complexity and firewall issues.
        

---

### 🌐 Modern VPN Protocols:

- **TLS (Transport Layer Security) VPNs**
    
    - Work at the **application layer**.
        
    - Use **port 443 (HTTPS)** — widely allowed through firewalls.
        
    - Compatible with any system that has a web browser.
        
    - Common choice for **remote user VPNs**.
        
- **HTML5 VPNs**
    
    - Web-based interface.
        
    - Users access internal resources **through a web server proxy**.
        
    - Does _not_ establish a direct presence on the internal network.
        

---

## 📌 Tunneling Approaches

When setting up **remote access VPNs**, administrators choose between:

### 🔷 Full-Tunnel VPN:

- All outbound traffic from the remote device goes through the VPN.
    
- Protects:
    
    - Corporate network traffic.
        
    - Internet browsing and all other activity.
        
- Provides maximum security but increases load on VPN infrastructure.
    

### 🔷 Split-Tunnel VPN:

- Some traffic (e.g., destined for corporate resources) goes through the VPN.
    
- Other traffic (e.g., regular Internet browsing) goes directly through the user’s local network.
    
- Benefits:
    
    - Reduces burden on VPN servers.
        
    - Conserves bandwidth.
        
- Routing policy is controlled by the VPN administrator.

## 📌 IDS (Intrusion Detection System) Errors

IDS can make mistakes, and monitoring these errors is crucial for effective security operations.

### Types of Errors:

- ❌ **False Positive:**
    
    - The IDS alerts administrators about an attack that **did not actually happen**.
        
    - Consequences:
        
        - Wastes administrator time investigating.
            
        - Can lead to alert fatigue, where real alerts are ignored.
            
- ❌ **False Negative:**
    
    - An actual attack occurs but the IDS **does not detect it**.
        
    - Consequences:
        
        - Attack proceeds undetected.
            
        - Poses serious risk to the organization.
            

---

## 📌 IPS (Intrusion Prevention System) Configurations

IPS can be deployed in different ways depending on how actively it should block traffic.

### Deployment Approaches:

- 🔷 **In-Band (Inline) Deployment**
    
    - IPS is placed **directly in the network path**.
        
    - All traffic passes **through** the IPS.
        
    - Advantages:
        
        - Can block suspicious traffic in real-time before it reaches its destination.
            
    - Risks:
        
        - IPS becomes a **single point of failure** — if it malfunctions, it can disrupt all communications.
            
- 🔷 **Out-of-Band (Passive) Deployment**
    
    - IPS is placed **outside the network path**.
        
    - Connected to a **SPAN (mirror) port** on a switch to receive **copies** of network traffic.
        
    - Advantages:
        
        - Cannot disrupt live traffic directly.
            
        - Can still react by sending commands to block future malicious traffic.
            
    - Limitation:
        
        - Cannot stop the **initial attack** — only future attempts.
## 📌 Benefits of the Cloud

When determining the right **on-premises vs. cloud balance**, understanding the benefits of cloud computing helps organizations make informed decisions.

### Key Benefits:

- 🔷 **On-Demand Self-Service:**
    
    - Cloud resources are available whenever needed.
        
    - Enables agility and faster deployment for developers and technologists.
        
- 🔷 **Scalability:**
    
    - Allows resources to grow as demand increases.
        
    - Two types:
        
        - **Vertical Scaling:** Increase the capacity of a single server (e.g., more CPUs, memory).
            
        - **Horizontal Scaling:** Add more servers to a cluster to support higher load.
            
- 🔷 **Elasticity:**
    
    - Similar to scalability but emphasizes **expanding and contracting capacity dynamically** to match needs.
        
    - Optimizes costs by adding resources during peak and removing them afterward.
        
- 🔷 **Measured Service:**
    
    - Cloud usage is tracked (compute time, storage, etc.).
        
    - Pay only for what you use — no more, no less.
        
- 🔷 **Agility & Flexibility:**
    
    - Rapid provisioning of resources and temporary environments.
        
    - Enables quick experimentation and innovation at low cost.
        

---

## 📌 Cloud Roles

In a cloud environment, different entities play different roles:

### 🏷 Roles Defined:

- 🌥 **Cloud Service Providers:**
    
    - Organizations that offer cloud services for sale (e.g., AWS, Azure).
        
- 👩‍💼 **Cloud Consumers:**
    
    - Organizations or individuals who **purchase and use cloud services**.
        
- 🤝 **Cloud Partners / Brokers:**
    
    - Provide support services like:
        
        - Training, consulting, integration, or custom development.
            
    - Help customers utilize and optimize cloud offerings.
        
- 🔍 **Cloud Auditors:**
    
    - Independent entities that assess and evaluate cloud services.
        
    - Can review general operations or focus specifically on security controls.
        
- 📡 **Cloud Carriers:**
    
    - Provide the **network connectivity** that links cloud providers and consumers..


## 📌 Virtualization Security

### Key Risks:

- 🔷 **Virtual Machine Escape:**
    
    - Attacker on one VM breaks out of its boundaries and accesses resources of another VM.
        
    - Exploits flaws in the **hypervisor**, which is supposed to isolate VMs.
        
- 🔷 **Virtual Machine Sprawl:**
    
    - Occurs when unused or forgotten VM instances are left running.
        
    - Results in:
        
        - Unnecessary costs.
            
        - Unpatched, vulnerable systems.
            
    - Solution: Maintain **instance awareness** and enforce clean-up procedures.
        

---

## 📌 Cloud Application Security

### Security Techniques & Tools:

- 🔷 **APIs & Security:**
    
    - APIs are heavily used for integration & interoperability.
        
    - Risks:
        
        - Insecure requests.
            
    - Mitigation:
        
        - Use API inspection technology (often via **Web Application Firewalls - WAFs**).
            
- 🔷 **Secure Web Gateways (SWGs):**
    
    - Monitor and enforce web access policies.
        
    - Block access to malicious or unauthorized web content.
        
- 🔷 **Cloud Access Security Brokers (CASBs):**
    
    - Act as intermediaries between users and cloud providers.
        
    - Enforce policies & monitor activity.
        

#### CASB Deployment Modes:

|Mode|How It Works|Pros & Cons|
|---|---|---|
|**Inline CASB**|Resides in the connection path (via appliance or agent)|Can block requests in real-time; requires network or endpoint config|
|**API-based CASB**|Communicates directly with cloud provider via APIs|No device config needed; cannot block requests in real-time|

---

## 📌 Resource Policies

- Offered by cloud providers to control user actions.
    
- Examples:
    
    - Restricting access to specific geographic regions.
        
    - Limiting which services users can use.
        
    - Preventing launch of large (costly) instances.
        
- Helps reduce risk from:
    
    - Accidental commands.
        
    - Compromised accounts.
        
    - Malicious insiders.
        

---

## 📌 Hardware Security Modules (HSMs)

- Dedicated, secure devices for managing encryption keys & cryptographic operations.
    
- Benefits:
    
    - High level of security.
        
    - Keys are never exposed to humans.
        
- Use Cases:
    
    - Internal key management by cloud providers.
        
    - Customer-accessible HSM services offered by cloud providers.
        
- Downsides:
    
    - Expensive to acquire & operate
## 📌 Symmetric Key Cryptography

### Weaknesses:

- 🔷 **Key Distribution:**
    
    - Parties must securely exchange the secret key _before_ communication begins.
        
    - If no secure electronic channel exists, offline (out-of-band) methods are required.
        
- 🔷 **No Nonrepudiation:**
    
    - Since all parties share the same secret key, it’s impossible to prove who sent a given message.
        
- 🔷 **Poor Scalability:**
    
    - In large groups, every pair of users would need a unique shared key.
        
    - The number of keys grows rapidly as group size increases.
        
- 🔷 **Frequent Key Regeneration:**
    
    - Every time someone leaves the group, the keys must be changed to maintain security.
        

---

## 📌 Asymmetric Key Cryptography

### Strengths:

- 🔷 **Scalability:**
    
    - Adding a new user only requires generating a single public–private key pair.
        
    - Same key pair is used to communicate securely with everyone.
        
- 🔷 **User Removal:**
    
    - Keys can be revoked without impacting others.
        
    - If a private key is compromised, only that key needs to be regenerated.
        
- 🔷 **Integrity, Authentication, Nonrepudiation:**
    
    - Messages signed with a private key can:
        
        - Prove the sender’s identity.
            
        - Ensure message integrity.
            
        - Prevent sender from denying the message later.
            
- 🔷 **Simple Key Distribution:**
    
    - Users just publish their public keys.
        
    - No need for preexisting secure channels or prior relationships.
        
    - Private key remains secret and cannot be derived from the public key.

## 📌 Goals of Digital Signatures

✅ **Authenticity & Nonrepudiation:**

- Assures the recipient that the message **came from the claimed sender**.
    
- Prevents the sender from later denying they sent the message.
    

✅ **Integrity:**

- Assures the recipient that the message **was not altered** during transmission.
    
- Protects against:
    
    - Malicious modification (e.g., tampering).
        
    - Unintentional modification (e.g., transmission errors).
        

---

## 📌 How Digital Signatures Work

### Key Concepts:

- Combines:
    
    - 🔷 **Public Key Cryptography**
        
    - 🔷 **Hashing Functions**
        

---

### 🔷 Sender’s (Alice’s) Process:

1️⃣ Alice generates a **message digest** of the plaintext message using a secure hashing algorithm (e.g., SHA-3).  
2️⃣ She encrypts **only the digest** using her **private key** — this becomes the **digital signature**.  
3️⃣ Alice appends the signature to the plaintext message.  
4️⃣ Alice sends both the message and signature to Bob.

---

### 🔷 Recipient’s (Bob’s) Process:

1️⃣ Bob decrypts the signature using Alice’s **public key**, revealing Alice’s original digest.  
2️⃣ Bob computes his own message digest of the received plaintext using the same hash function.  
3️⃣ Bob compares the two digests:

- If they **match** → Message is authentic and unmodified.
    
- If they **don’t match** → Message was tampered with or not sent by Alice.


# Digital Certificates & Certificate Authorities

## 📌 What are Digital Certificates?

- Provide assurance that a public key belongs to the claimed individual or entity.
    
- Function as **endorsed copies of a public key**, signed by a trusted **Certificate Authority (CA)**.
    
- When a certificate is verified as signed by a trusted CA, the public key is considered **legitimate**.
    

---

## 📌 Standards & Structure

- Governed by the **X.509 standard**.
    
- X.509 certificates include these key attributes:
    
    - 🔷 **Version:** of X.509 standard used.
        
    - 🔷 **Serial Number:** issued by the certificate creator.
        
    - 🔷 **Signature Algorithm Identifier:** specifies the algorithm used by the CA to sign the certificate.
        
    - 🔷 **Issuer Name:** identifies the CA that issued the certificate.
        
    - 🔷 **Validity Period:** start date/time & expiration date/time.
        
    - 🔷 **Subject Common Name (CN):** clearly identifies the certificate owner (e.g., `certmike.com`).
        
    - 🔷 **Subject Alternative Names (SAN):** (optional) additional IPs, domains, etc., protected by the certificate.
        
    - 🔷 **Subject’s Public Key:** the actual public key used to establish secure communications.
        

---

## 📌 Common Uses of Certificates

- Verify the public keys of:
    
    - Computers/servers (e.g., for HTTPS websites).
        
    - Individual users.
        
    - Email addresses.
        
    - Developers (code-signing certificates).
        

---

## 📌 Certificate Authorities (CAs)

- Neutral organizations that **notarize digital certificates** by validating identity.
    
- Critical to maintaining trust in the **Public Key Infrastructure (PKI)**.
    
- To obtain a certificate, the requester must prove their identity to the CA.
    

---

### Examples of Major CAs:

✅ Symantec  
✅ IdenTrust  
✅ Amazon Web Services  
✅ GlobalSign  
✅ Comodo  
✅ Certum  
✅ GoDaddy  
✅ DigiCert  
✅ Secom  
✅ Entrust  
✅ Actalis  
✅ Trustwave

## phases of Software Development

These phases appear in most **Software Development Life Cycle (SDLC)** models:

---

### 1️⃣ **Feasibility**

- Investigates whether the effort is viable.
    
- Examines alternative solutions & high-level costs.
    
- Results in a **recommendation & plan**.
    

---

### 2️⃣ **Analysis & Requirements Definition**

- Engages customers to define:
    
    - Desired functionality.
        
    - Gaps in current systems.
        
    - Improvements & priorities.
        
- Defines **security requirements** and promotes **secure coding practices**.
    

---

### 3️⃣ **Design**

- Covers:
    
    - Functionality design.
        
    - Architecture & integration techniques.
        
    - Dataflows & business processes.
        
    - Other design elements.
        

---

### 4️⃣ **Development**

- Actual **coding** of the application.
    
- Includes **unit testing** of components.
    

---

### 5️⃣ **Testing & Integration**

- Integrates individual units & tests overall functionality.
    
- Includes:
    
    - Integration with external services & data sources.
        
    - **User Acceptance Testing (UAT)** to confirm user satisfaction.
        

---

### 6️⃣ **Training & Transition**

- Ensures end-users are trained.
    
- Software enters general use.
    
- Also called:
    
    - **Acceptance phase**
        
    - **Installation & Deployment phase**
        

---

### 7️⃣ **Operations & Maintenance**

- Longest phase.
    
- Includes:
    
    - Ongoing support.
        
    - Patching & updates.
        
    - Minor modifications.
        

---

### 8️⃣ **Disposition**

- End-of-life phase for the system.
    
- Reasons for this phase:
    
    - Cost savings.
        
    - Knowledge transfer for replacement tools.
        
    - Proper preservation or destruction of data.
        

---

## 📌 Software Environments

### Development → Test → Staging → Production

- 🔷 **Development Environment**
    
    - Used by developers.
        
    - Can be individual or shared.
        
- 🔷 **Test Environment**
    
    - QA & testing without impacting production.
        
    - Sometimes called **preproduction**.
        
- 🔷 **Staging Environment**
    
    - Transitional area for code that passed testing.
        
    - Prepares for deployment into production.
        
- 🔷 **Production Environment**
    
    - The **live system** used by end-users

## 📌 Waterfall Model

### Characteristics:

- Sequential, **phase-by-phase** development.
    
- Phases do **not overlap** — each phase must be completed before moving to the next.
    
- Best suited for projects with:
    
    - Fixed scope.
        
    - Known timeframe.
        
    - Stable, well-understood technology.
        

---

### Typical Waterfall Phases:

1️⃣ **Requirements Gathering**

- Document all business and technical requirements.
    

2️⃣ **Analysis**

- Develop business rules & models.
    

3️⃣ **Design**

- Create the software architecture.
    

4️⃣ **Coding & Integration**

- Implement and integrate the software.
    

5️⃣ **Testing & Debugging**

- Validate and ensure the software works as intended.
    

6️⃣ **Operational Phase**

- Ongoing support, maintenance, and operations.
    

---

### Advantages & Disadvantages:

✅ Simple, structured, and predictable.  
❌ Inflexible — not responsive to changes; no internal iteration.  
❌ Not ideal when requirements evolve during development.

---

## 📌 Spiral Model

### Characteristics:

- Combines Waterfall’s **linear structure** with **iterative cycles**.
    
- Revisits phases multiple times to refine requirements and design.
    
- Places strong emphasis on **risk assessment & management**.
    
- More flexible than Waterfall — accommodates changes and feedback.
    

---

### Spiral Phases (repeated in cycles):

1️⃣ **Identification (Requirements Gathering)**

- Gather initial and increasingly detailed requirements.
    

2️⃣ **Design**

- Conceptual, architectural, logical, and physical design.
    

3️⃣ **Build**

- Proof of concept → iterative builds → final production release.
    

4️⃣ **Evaluation**

- Risk analysis & feasibility assessment.
    
- Customer testing & feedback for acceptance.
    

---

### Advantages & Disadvantages:

✅ Handles changing requirements & external feedback well.  
✅ Encourages early development and risk assessment.  
❌ Can result in **rework** if new requirements emerge late.  
❌ May identify major design changes late in the process.

---

## 📌 Agile (Intro)

- Agile is an **iterative and incremental** development methodology.
    
- Focuses on **flexibility**, **customer collaboration**, and **responding to change**.
    
- More details about Agile likely follow in the next section.


## verview

- Agile is an **iterative & incremental** process.
    
- Unlike **Waterfall** and **Spiral**, Agile is not linear and does not rely heavily on upfront planning & documentation.
    
- Based on the _Manifesto for Agile Software Development_ — emphasizing adaptability, collaboration, and customer focus.
    

---

## 📌 Agile Manifesto — 4 Core Values

1️⃣ **Individuals & interactions > Processes & tools**  
2️⃣ **Working software > Comprehensive documentation**  
3️⃣ **Customer collaboration > Contract negotiation**  
4️⃣ **Responding to change > Following a plan**

---

## 📌 How Agile Works

- Breaks work into **smaller units**.
    
- Focuses on adapting to changing needs & priorities.
    
- Work is structured into **short cycles** called **sprints**:
    
    - Sprints last from a few days to a few weeks.
        
    - Developers & customers agree when the task is done — or when sprint time ends.
        

---

## 📌 Agile Principles (12 Principles)

✅ Ensure **customer satisfaction** via early & continuous delivery.  
✅ Welcome **changing requirements**, even late in development.  
✅ Deliver working software **frequently** (weeks, not months).  
✅ Encourage **daily collaboration** between developers & businesspeople.  
✅ Build projects around **motivated individuals**, providing support & trust.  
✅ Prefer **face-to-face conversation** for communication.  
✅ Measure progress via **working software**.  
✅ Maintain a **sustainable development pace**.  
✅ Focus on **technical excellence** & good design.  
✅ Embrace **simplicity** — maximize work _not done_.  
✅ Best results come from **self-organizing teams**.  
✅ Teams should **reflect regularly** & adjust to become more effective.

---

## 📌 Advantages of Agile

- Less formal than Waterfall & Spiral.
    
- Allows frequent customer feedback & revisions.
    
- More nimble & responsive to problems.
    
- Faster customer feedback — particularly useful when addressing security issues.
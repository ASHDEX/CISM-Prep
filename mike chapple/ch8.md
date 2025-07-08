## 📌 Key Definitions

### 🔷 **Event**

- Any **observable occurrence** in a system or network.
    
- Examples:
    
    - User accessing a file.
        
    - Administrator changing folder permissions.
        
    - Attacker conducting a port scan.
        

---

### 🔷 **Security Event**

- Any observable occurrence that is **related to a security function**.
    
- Examples:
    
    - Same as above but with a security context (e.g., unauthorized file access).
        

---

### 🔷 **Adverse Event**

- Any event with **negative consequences**.
    
- Examples:
    
    - Malware infection.
        
    - Server crash.
        
    - Unauthorized file access.
        

---

### 🔷 **Security Incident**

- A **violation** or **imminent threat of violation** of:
    
    - Computer security policies.
        
    - Acceptable use policies.
        
    - Standard security practices.
        
- Examples:
    
    - Loss of sensitive information.
        
    - Intrusion into a system.
        
    - Keylogger deployed to steal credentials.
        
    - Denial-of-service (DoS) attack.
        

---

### 📌 Relationship

✅ Every **security incident** involves **one or more security events**.  
❌ Not every **security event** escalates to a security incident.

---

## 📌 CSIRT (Computer Security Incident Response Team)

- Responsible for responding to **security incidents** within an organization.
    
- Actions include:
    
    - Following standardized **response procedures**.
        
    - Applying subject matter expertise & professional judgment.
-## 📌 Detection & Analysis Phase

### Key Points:

- One of the most **difficult & critical phases** of incident response.
    
- Requires both tools & the trained judgment of experienced analysts.
    

---

### 🔷 NIST 800-61: Four Categories of Indicators

1️⃣ **Alerts**

- From IDS/IPS, SIEMs, antivirus, file integrity checkers, or third-party services.  
    2️⃣ **Logs**
    
- OS, applications, services, network devices, and network flow logs.  
    3️⃣ **Public Info**
    
- Reports of new vulnerabilities & exploits from trusted sources.  
    4️⃣ **People**
    
- Employees, partners, or outsiders reporting suspicious activity.
    

---

### 🔷 Initial Validation

- Analysts must determine whether observed activity truly constitutes a **security incident** worth escalating.
    

---

### 🔷 Best Practices to Improve Detection & Analysis:

✅ Profile networks & systems — know what “normal” looks like.  
✅ Understand normal user & system behavior — including business cycles.  
✅ Establish a logging policy — specify what, where, and how long to log.  
✅ Perform event correlation — often via SIEM tools.  
✅ Synchronize clocks — use NTP for accurate log timestamps.  
✅ Maintain an internal knowledge base — with system profiles & usage patterns.  
✅ Start capturing network traffic when an incident is suspected.  
✅ Use filters to reduce data noise during investigations.  
✅ Seek external help when needed — from quick research to engaging other response teams.

---

## 📌 Containment, Eradication & Recovery Phase

### Objectives:

- Select & implement an appropriate **containment strategy**.
    
- Limit damage & prevent further spread.
    
- Gather evidence for response & potential legal action.
    
- Identify attacker(s) & compromised systems.
    
- Eradicate the incident’s effects & restore normal operations.
    

---

### 🔷 Containment

- Starts **as soon as an incident is confirmed**.
    
- Isolates affected systems & stops propagation.
    

---

### NIST Criteria for Choosing Containment Strategies:

🔷 Potential damage & theft risk.  
🔷 Need to preserve evidence.  
🔷 Service availability requirements.  
🔷 Time & resources required for the strategy.  
🔷 Effectiveness (partial vs full containment).  
🔷 Duration of the solution:

- Emergency workaround (hours).
    
- Temporary workaround (weeks).
    
- Permanent solution. 


## 📌 Purpose of Segmentation

- Used proactively to limit the **spread of security incidents**.
    
- Helps contain damage by isolating specific systems or attackers.
    

---

## 📌 Two Primary Isolation Techniques

### 🔷 1️⃣ **Isolating Affected Systems**

- Takes segmentation to the next level during an incident.
    
- Steps:
    
    - Disconnect compromised systems from the rest of the network.
        
    - These systems **may still communicate with each other** and potentially the attacker over the Internet.
        
- Goal: Prevent further impact on unaffected systems & data.
    

---

### 🔷 2️⃣ **Isolating the Attacker**

- A more advanced strategy.
    
- Involves placing the attacker into a **sandboxed environment**:
    
    - Sandbox contains **no sensitive data or resources**.
        
    - Allows defenders to monitor the attacker’s behavior safely.
        
    - Useful for gathering intelligence on attack techniques & objective

## 📌 Evidence Gathering & Handling

### Key Objective During Containment:

- Limit damage to the organization.
    
- But also gather evidence that may:
    
    - Aid internal analysis.
        
    - Support legal proceedings.
        

---

### When Evidence May Be Used in Court:

- Incident handlers must take **special care** to preserve and document evidence properly.
    
- Improper handling may make evidence **inadmissible**.
    

---

### NIST Recommendations: Maintain an Evidence Log

✅ Identifying information:

- Location, serial number, model number, hostname, MAC address, IP address.
    

✅ Name, title, and phone number of **each individual** who collected or handled the evidence.

✅ **Time & date (including time zone)** of every evidence handling event.

✅ Locations where the evidence was stored at all times.

---

### Why It Matters:

- Failure to maintain accurate logs undermines the **chain of custody**, risking inadmissibility of evidence in court.
    

---

## 📌 Recovery Phase

### Purpose:

- Restore **normal capabilities & services** after containment and eradication.
    
- Ensure the rebuilt systems are **more secure** and less vulnerable to future attacks.
    

---

### Recovery Activities:

✅ Rebuild & patch compromised systems.  
✅ Reconfigure firewalls.  
✅ Update malware signatures.  
✅ Correct security control weaknesses that enabled the attack.  
✅ Reconstitute resources while improving security posture


## 📌 Levels of Data Sanitization

Listed in increasing order of **effectiveness**, **cost**, and **difficulty**:

### 🔷 1️⃣ **Clear**

- Uses **logical techniques** to sanitize data from all user-addressable storage.
    
- Protects against **simple, non-invasive recovery techniques**.
    
- Methods:
    
    - Overwriting with new values.
        
    - Factory reset via menu options.
        
- Typically uses standard **Read & Write commands**.
    

---

### 🔷 2️⃣ **Purge**

- Uses **physical or logical techniques** to make data recovery infeasible even with advanced laboratory methods.
    
- Examples:
    
    - Overwriting or block erasure using dedicated device commands.
        
    - Cryptographic erase.
        
    - Degaussing — applies strong magnetic fields to disrupt data.
        

---

### 🔷 3️⃣ **Destroy**

- Completely destroys the media so it **cannot store data again**.
    
- Makes recovery impossible even with state-of-the-art techniques.
    
- Methods:
    
    - Disintegration.
        
    - Pulverization.
        
    - Melting.
        
    - Incineration.
        

---

### 🔷 Validation After Sanitization

- After **clear**, **purge**, or **destroy**, validate that:
    
    - Media is fully sanitized.
        
    - No residual data remains.
        

---

## 📌 Validating the Recovery Effort

Before completing recovery, ensure all measures were effective.  
Include these **four essential activities**:

1️⃣ **Validate Accounts**

- Confirm that only **authorized user accounts** exist.
    
- Use periodic account reviews to support this.
    

2️⃣ **Verify Permissions**

- Check that accounts have only the **least privilege necessary**.
    
- Ensure no excessive permissions for user, admin, or service accounts.
    

3️⃣ **Confirm Logging**

- Verify all systems & apps log appropriately to meet the organization’s policy.
    
- Logs should reach and be archived in a centralized repository.
    

4️⃣ **Conduct Vulnerability Scans**

- Run comprehensive scans.
    
- Initiate remediation for any vulnerabilities found.
## 📌 Incident Response Policy — NIST Recommendations

### Key Elements of a Policy:

✅ **Statement of Management Commitment**

- Demonstrates support from leadership.
    

✅ **Purpose & Objectives**

- Clearly defines the intent of the policy.
    

✅ **Scope**

- Specifies **who** it applies to and under **what circumstances**.
    

✅ **Definitions**

- Clarifies terms like “cybersecurity incident.”
    

✅ **Organizational Structure**

- Defines **roles, responsibilities, and authority levels.**
    

✅ **Incident Prioritization/Severity Rating Scheme**

- Helps assess and rank incidents by impact & urgency.
    

✅ **Performance Measures**

- Defines metrics for evaluating the CSIRT's effectiveness.
    

✅ **Reporting & Contact Forms**

- Provides clear methods for reporting incidents and contacting the team.
    

---

## 📌 Procedures & Playbooks

### Procedures:

- Provide **detailed, tactical instructions** for CSIRT members.
    
- Capture the collective experience of the team & experts.
    
- Developed during calm periods and ready to deploy during crises.
    

### Playbooks:

- Specific procedures tailored for **particular types of incidents**.
    
- Example Playbooks for a financial institution might cover:  
    🔷 Breach of personal financial information.  
    🔷 Web server defacement.  
    🔷 Phishing attack targeting customers.  
    🔷 Loss of a laptop.  
    🔷 General incident not otherwise specified.
    

---

## 📌 CSIRT Composition

The CSIRT may include members from the following areas:

- 🔷 **Technical SMEs**:
    
    - System engineers, network & database admins, desktop & application experts.
        
- 🔷 **IT Support Staff**:
    
    - Executes actions directed by CSIRT.
        
- 🔷 **Legal Counsel**:
    
    - Ensures actions comply with laws & policies.
        
    - Advises on regulatory communications.
        
- 🔷 **Human Resources**:
    
    - Investigates potential employee misconduct.
        
- 🔷 **Public Relations & Marketing**:
    
    - Manages communications with media and the public.
The **impact of an incident** depends on:

- The degree of impairment to the organization.
    
- The effort required for recovery.
    

---

## 📌 Functional Impact

Measures how the incident affects **services & operations**.  
NIST’s recommended **functional impact categories**:

|**Category**|**Definition**|
|---|---|
|**None**|No effect on providing all services to all users.|
|**Low**|Minimal effect; all critical services still available but with reduced efficiency.|
|**Medium**|Loss of a critical service to a subset of users.|
|**High**|Loss of some critical services to all users.|

---

## 📌 Economic Impact

Measures **financial loss** from the incident.  
Organizations should adjust thresholds based on size & tolerance.

|**Category**|**Definition**|
|---|---|
|**None**|Negligible financial impact.|
|**Low**|≤ $10,000.|
|**Medium**|> $10,000 and < $500,000.|
|**High**|≥ $500,000.|

---

## 📌 Recoverability Effort

Measures the **time & resources** needed for recovery.  
NIST’s recommended **recoverability effort categories**:

|**Category**|**Definition**|
|---|---|
|**Regular**|Predictable recovery using existing resources.|
|**Supplemented**|Predictable recovery with additional resources.|
|**Extended**|Unpredictable recovery; needs external help.|
|**Not Recoverable**|Recovery impossible (e.g., data leaked publicly); launch investigation.|

---

## 📌 Data Impact

Considers the **type of data** affected and its sensitivity.

### NIST’s **Information Impact Categories**:

|**Category**|**Definition**|
|---|---|
|**None**|No data compromised.|
|**Privacy Breach**|PII accessed/exfiltrated.|
|**Proprietary Breach**|Unclassified proprietary info accessed/exfiltrated.|
|**Integrity Loss**|Sensitive/proprietary info modified or deleted.|

---

### Alternative **Private Organization Data Impact Categories**:

|**Category**|**Definition**|
|---|---|
|**None**|No data compromised.|
|**Regulated Information Breach**|Data subject to compliance (e.g., PII, PHI, PCI, GDPR SPI) accessed/exfiltrated.|
|**Intellectual Property Breach**|Trade secrets or sensitive R&D data accessed/exfiltrated.|
|**Confidential Information Breach**|Sensitive internal corporate data (e.g., financials, M&A plans) accessed/exfiltrated.|
|**Integrity Loss**|Data was altered or deleted.|

---

### Notes:

- NIST’s definitions skew toward government data types; private orgs should customize to fit their context.
    
- Financial and information impact scales should reflect organizational risk tolerance and regulatory obligations.


## 📌 Types of Investigations

### 🔷 Administrative Investigations

- Internal investigations into operational issues or policy violations.
    
- Conducted by internal staff, possibly for HR or disciplinary purposes.
    

#### Types:

✅ **Operational Investigations**

- Aim: Resolve technical or operational problems (e.g., server performance issues).
    
- Loosest standards of evidence collection.
    
- May include **root cause analysis** to prevent recurrence.
    
- Can transition into criminal or other investigations if malfeasance is uncovered.
    

✅ **Non-Operational Administrative Investigations**

- Aim: Investigate employee misconduct or other non-technical issues.
    
- Require stronger evidence standards.
    
- Consult **sponsors & legal team** for appropriate evidence handling.
    

---

### 🔷 Criminal Investigations

- Led by law enforcement.
    
- Investigate alleged **criminal law violations**.
    
- Must meet **beyond a reasonable doubt** standard.
    
- Requires strict evidence handling & preservation.
    

---

### 🔷 Civil Investigations

- Internal or external legal teams.
    
- Aim: Resolve disputes between parties in civil court.
    
- Standard of proof: **preponderance of evidence** (more likely than not).
    
- Evidence standards less rigorous than criminal.
    

---

### 🔷 Regulatory Investigations

- Conducted by government agencies to enforce **administrative law**.
    
- Vary in scope, standards align with venue of adjudication.
    

---

### 🔷 Industry Standard Investigations

- Enforce **contractual obligations** (e.g., PCI DSS compliance).
    
- May involve independent audits or assessments.
    
- Non-compliance can result in fines or sanctions.
    

---

## 📌 Electronic Discovery (eDiscovery)

- Legal obligation to preserve & share **electronic evidence**.
    
- Guided by the **Electronic Discovery Reference Model (EDRM)**:  
    1️⃣ **Information Governance** — Organize info for future discovery.  
    2️⃣ **Identification** — Locate relevant information.  
    3️⃣ **Preservation** — Protect data from alteration/deletion.  
    4️⃣ **Collection** — Gather relevant data centrally.  
    5️⃣ **Processing** — Remove irrelevant information (“rough cut”).  
    6️⃣ **Review** — Assess for relevance & privilege.  
    7️⃣ **Analysis** — Deeper inspection for context/content.  
    8️⃣ **Production** — Prepare data for sharing.  
    9️⃣ **Presentation** — Present data in court or to other parties.
    
- Requires **coordination between IT and legal teams**.
    
- More on EDRM: edrm.net
    

---

## 📌 Evidence in Legal Proceedings

- Evidence = **artifacts** (e.g., devices, logs, data).
    
- Used to prove guilt beyond a reasonable doubt in criminal cases.
    
- Must meet admissibility, integrity, and chain of custody requirements.

## 📌 Overview

- To prosecute a crime, prosecutors must prove guilt **beyond a reasonable doubt**.
    
- Evidence (artifacts) may include:
    
    - Physical devices (computers, mobile devices).
        
    - Logs & data.
        
    - Other digital/physical records.
        
- Reference: [NIST SP 800-86](https://www.nist.gov/publications/guide-integrating-forensic-techniques-incident-response)
    

---

## 📌 Admissible Evidence: Three Requirements

For evidence to be allowed in court, it must be:  
✅ **Relevant** — helps determine a fact in the case.  
✅ **Material** — directly related to the case.  
✅ **Competent** — obtained legally.

---

## 📌 Types of Evidence

### 🔷 1️⃣ **Real Evidence (Object Evidence)**

- Physical objects brought into court.
    
- Examples:
    
    - Weapon, seized computer, hard drive.
        
- Must be:
    
    - Relevant, material, competent.
        
    - Authenticated — shown to be unique & unaltered.
        
- If unique identification is not possible → use a **chain of custody**.
    

---

### 🔷 2️⃣ **Documentary Evidence**

- Written materials used to prove a fact.
    
- Must be:
    
    - Relevant, material, competent.
        
    - Authenticated (e.g., log verified by admin as routine business record).
        
- Special rules:
    
    - **Best Evidence Rule**: Original document required unless exceptions apply.
        
    - **Parol Evidence Rule**: Written agreements override verbal agreements.
        

---

### 🔷 3️⃣ **Testimonial Evidence**

- Witness testimony — verbal in court or written deposition.
    
- Witnesses:
    
    - Must swear to tell the truth.
        
    - Must have personal knowledge.
        
    - Must recall basis of their testimony (notes are allowed).
        
- Types:
    
    - **Direct Evidence**: Based on firsthand observation.
        
    - **Expert Opinion**: If accepted as an expert, may offer opinion beyond direct observation.
        

---

### 🔷 4️⃣ **Demonstrative Evidence**

- Not explicitly detailed here but usually includes diagrams, models, or other aids that help illustrate or explain facts to the court.
    

---

## 📌 Chain of Custody

- Documents all handling of evidence to prove it remained untampered.
    
- Must maintain an **unbroken sequence** from collection to courtroom.
    
- Evidence labels/logs should include:
    
    - General description.
        
    - Time & date of collection.
        
    - Exact location of collection.
        
    - Name of person collecting.
        
    - Circumstances of collection.
        
- Every handler signs the log when taking & releasing custody.
    

---

## 📌 Hearsay Rule & Exceptions

- **Hearsay**: Testimony about what someone else said outside court → generally inadmissible.
    
- Exceptions:
    
    - Past sworn testimony from an unavailable witness.
        
    - Statements against interest.
        
    - Dying declarations.
        
    - Public records.
        
    - **Business Records Exception**:
        
        - Logs/system records admissible if:
            
            - Created at time of event.
                
            - By someone/system with direct knowledge.
                
            - In regular course of business.
                
        - Must be accompanied by testimony confirming these criteria.

## 📌 Demonstrative Evidence

- Supports **testimonial evidence** by clarifying or explaining concepts.
    
- Examples:
    
    - Diagram of a network packet.
        
    - Illustration of a DDoS attack process.
        
- Admissibility:
    
    - Determined by the trial court.
        
    - Must assist the jury in understanding the case.
        

---

## 📌 Artifacts & Digital Evidence

- Artifacts = evidence items (e.g., devices, logs, memory dumps).
    
- Collection should be performed by **trained forensic technicians**.
    

---

## 📌 IOCE (International Organization on Computer Evidence) Principles

✅ Apply general forensic & procedural principles to digital evidence.  
✅ Do not alter evidence when seizing it.  
✅ Only trained personnel may access original evidence.  
✅ Fully document, preserve, and make available all actions.  
✅ Individual handlers are responsible for their actions.  
✅ Agencies are responsible for compliance with these principles.

---

## 📌 Forensic Best Practices

- Preserve the **original evidence**; work on copies.
    
- Example:
    
    - Image a hard drive → seal original → analyze the image.
        

---

## 📌 Forensic Techniques

### 🔷 Media Analysis

- Examines storage media (magnetic, optical).
    
- Techniques:
    
    - Recover deleted files from unallocated sectors.
        
    - Analyze forensic images.
        
    - Use write blockers to prevent altering original media.
        
- Steps:  
    1️⃣ Power off & remove the drive.  
    2️⃣ Attach to forensic workstation via write blocker.  
    3️⃣ Hash contents.  
    4️⃣ Create forensic image & hash it.  
    5️⃣ Analyze only copies of the image.
    

---

### 🔷 In-Memory Analysis

- Collects memory from a live system (volatile).
    
- Use trusted tools to create a memory dump → store on forensically-prepared media.
    
- Compute & verify hash of memory dump.
    
- Work only on copies of the dump file.
    

---

### 🔷 Network Analysis

- Examines network activity during an incident.
    
- Relies on:
    
    - IDS/IPS logs, firewall logs.
        
    - Flow data.
        
    - Packet captures.
        
- Methods:
    
    - Use SPAN port or network tap for packet capture.
        
    - Store captures on forensically-prepared media & hash them.
        
    - Avoid altering live traffic.
        

---

### 🔷 Software Analysis

- Reviews application activity & code for:
    
    - Backdoors, logic bombs.
        
    - SQL injections, privilege escalations.
        
- Uses:
    
    - Application logs.
        
    - File hash validation (via NIST’s NSRL — [National Software Reference Library](https://www.nist.gov/itl/ssd/software-quality-group/national-software-reference-library-nsrl)).
        

---

### 🔷 Hardware/Embedded Device Analysis

- Examines:
    
    - PCs, smartphones, tablets.
        
    - Embedded systems (e.g., cars, security devices).
        
- Requires:
    
    - Specialized expertise in hardware, storage, & embedded OS.
        

---

### Notes:

- Always work on **copies**, preserve chain of custody, and compute & verify hashes.
    
- Label, log, and document every step thoroughly to ensure admissibility and integrity.
## 📌 Common Incident Response Test Types

### 🔷 Checklist Reviews

- Each team member receives their incident response checklist.
    
- Team members **walk through their expected actions**.
    
- Ensures:
    
    - Everyone understands their role.
        
    - Steps on checklist remain **accurate & relevant**.
        

---

### 🔷 Tabletop Exercises

- Team gathers in a central location.
    
- Discuss how they would respond to a **given scenario**.
    
- No actual actions taken — focuses on **discussion & planning**.
    

---

### 🔷 Incident Simulations

- More advanced than tabletop exercises.
    
- Team is asked to **carry out some or all portions of the response** to a provided scenario.
    
- Tests both planning and execution in a controlled environment.
    

---

## 📌 Key Incident Response Metrics

### Metrics to Measure & Track:

✅ **Number of incidents handled**.  
✅ **Total labor hours spent per incident**.  
✅ **Time from incident start to discovery**.  
✅ **Time from discovery to initial impact assessment**.  
✅ **Elapsed time for each stage** of:

- Containment
    
- Eradication
    
- Recovery  
    ✅ **Time to respond to the initial report**.  
    ✅ **Time to escalate to management and/or external authorities**.  
    ✅ **Compliance with policies & procedures**.  
    ✅ **Was the cause of the incident identified?**  
    ✅ **Was the incident a recurrence?**  
    ✅ **Estimated monetary damage caused**.  
    ✅ **Difference between initial & final impact assessment**


# 📄 Vulnerability Scanning & Application Testing

## 📌 Vulnerability Scanning

### Factors Influencing Scan Frequency:

- **Risk Appetite:**
    
    - How much risk the organization is willing to tolerate.
        
    - Risk-averse organizations may scan more frequently to detect vulnerabilities quickly.
        
- **Regulatory Requirements:**
    
    - Standards like **PCI DSS** or **FISMA** may set minimum scanning frequencies.
        
    - Internal corporate policies may also mandate specific schedules.
        
- **Technical Constraints:**
    
    - Scanner’s capacity (e.g., limited number of scans per day).
        
    - Need to adjust schedule to ensure all scans complete successfully.
        
- **Business Constraints:**
    
    - Avoid running resource-intensive scans during peak business periods.
        
    - Prevent disruption of critical processes.
        
- **Licensing Limitations:**
    
    - May restrict bandwidth, number of simultaneous scans, or total number of scans allowed.
        

---

## 📌 Application Testing Techniques

When testing applications for vulnerabilities, three primary techniques are used:

### 1️⃣ **Static Testing**

- Analyzes **source code without executing it**.
    
- Benefits:
    
    - Directs developers to specific vulnerabilities.
        
    - Often includes detailed remediation advice.
        

### 2️⃣ **Dynamic Testing**

- Executes code and tests all interfaces exposed to the user.
    
- Uses a variety of inputs to identify vulnerabilities during runtime.
    

### 3️⃣ **Interactive Testing**

- Combines **static and dynamic testing**.
    
- Analyzes source code while testers interact with the application via its interfaces.


## 📌 Vulnerability Scanner Reports

### Types of Reports:

- **Positive Report** — Scanner reports a vulnerability _is present_:
    
    - ✅ **True Positive:** Vulnerability really exists.
        
    - ❌ **False Positive:** Reported vulnerability does **not** exist.
        
- **Negative Report** — Scanner reports a vulnerability _is not present_:
    
    - ✅ **True Negative:** Vulnerability really does **not** exist.
        
    - ❌ **False Negative:** Vulnerability actually exists, but scanner failed to detect it.
        

---

## 📌 Information Sources for Analysis

When validating and analyzing vulnerabilities, use:

- **Log Reviews**
    
    - From servers, applications, network devices, etc., to spot exploitation attempts.
        
- **Security Information and Event Management (SIEM) Systems**
    
    - Correlates logs from multiple sources and provides actionable intelligence.
        
- **Configuration Management Systems**
    
    - Lists operating systems and applications installed, helping assess exposure.
        

---

## 📌 Weak Configurations

Vulnerability scans may uncover **insecure configurations**, such as:

- 🔷 **Default Settings**
    
    - Example: Administrative setup pages left enabled in production.
        
- 🔷 **Unsecured Accounts**
    
    - Includes user or root accounts:
        
        - Without strong authentication.
            
        - Using default passwords.
            
- 🔷 **Unnecessary Open Ports & Services**
    
    - Only services essential for the system’s role should remain active.
        
- 🔷 **Excessive Permissions**
    
    - Users have more access than necessary (violating the principle of least privilege).
        

---

## 📌 Encryption

Encryption is a **critical control** to protect:

- Data **at rest**.
    
- Data **in transit**.
    

When implementing encryption, two key decisions must be made:  
1️⃣ **Algorithm:**

- The cryptographic method used for encryption and decryption.
    

2️⃣ **Encryption Key:**

- The secret or private key used with the chosen algorithm.

## 📌 Rules of Engagement (RoE)

Once the **type of assessment** and **tester’s knowledge level** are determined, the rest of the **RoE** can be written.

### Key Elements of RoE:

- 📆 **Timeline:**
    
    - When testing will occur.
        
    - May be scheduled during:
        
        - Non-critical hours (to minimize service impact).
            
        - Business hours (to observe defensive reactions).
            
- 🎯 **Scope:**
    
    - Which locations, systems, applications, or targets are:
        
        - **Included**
            
        - **Excluded**
            
    - Must account for third-party service providers (e.g., ISPs, SaaS vendors, outsourced monitoring).
        
- 🛠 **Technical Constraints:**
    
    - Any specific restrictions on tools, techniques, or resources.
        
- 🔒 **Data Handling:**
    
    - Confidentiality requirements for data and findings.
        
    - Encryption during & after testing.
        
    - Contractual obligations to securely dispose of data/results post-engagement.
        
- 🛡 **Expected Defensive Behaviors:**
    
    - Clarify whether defensive actions (e.g., shunning, blacklisting) are expected or should be avoided.
        
    - If the test is to evaluate defenses, these behaviors are desirable; if testing infrastructure resilience, they may hinder testing.
        
- 👥 **Resources Committed:**
    
    - Especially in **white-box** and **gray-box** tests, administrators, developers, and SMEs may need to participate actively.
        
- ⚖️ **Legal Concerns:**
    
    - Review relevant laws for:
        
        - Target organization
            
        - Remote locations
            
        - In-scope third-party providers
            
- 📣 **Communication Plan:**
    
    - Frequency of updates (e.g., daily, weekly, at completion).
        
    - Procedures if testers discover an _active compromise_ during testing.
        

---

## 📌 Permission to Test

- The tools & techniques used in penetration testing can be **illegal** if performed without **proper authorization**.
    
- Always secure **documented permission** before testing:
    
    - Examples of acceptable documentation:
        
        - Signed agreement.
            
        - Memo from senior management.
            
        - Written authorization (“get out of jail free” card).
            
- Why a “get out of jail free” card?
    
    - It’s the document you would show if something went wrong to prove you had permission.
        
    - Protects you from legal or organizational repercussion



## 📌 Fundamental Phases of a Test

### 1️⃣ **Initial Access**

- Attacker exploits a vulnerability to gain **entry into the organization’s network**.
    

### 2️⃣ **Privilege Escalation**

- Attacker uses techniques to gain **higher privileges** (e.g., root access) on the compromised system.
    

### 3️⃣ **Pivoting (Lateral Movement)**

- Attacker moves from the initially compromised system to **other systems** on the target network.
    

### 4️⃣ **Persistence**

- Attacker installs **backdoors or mechanisms** that allow them to regain access later, even if the initial vulnerability is patched.
    

---

## 📌 Roles in a Security Exercise

### 🔴 **Red Team**

- Acts as **attackers**.
    
- Objective: Attempt to gain unauthorized access to systems.
    

### 🔵 **Blue Team**

- Acts as **defenders**.
    
- Objective: Secure systems & networks, monitor for attacks, and deploy active defenses.
    
- Often given a **head start** to prepare before the attack phase begins.
    

### ⚪ **White Team**

- Acts as **observers and referees**.
    
- Responsibilities:
    
    - Settle disputes over the rules.
        
    - Document lessons learned.
        
    - Monitor both red and blue teams’ activities.
        
    - Ensure the exercise runs fairly and safely.
        

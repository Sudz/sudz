<!-- Badges -->
🌍 Passionate about building resilient, production-grade AI & data science solutions for Africa and beyond.

---

## 🚀 What I Do

- **Industrial Data Science & MLOps:** From rapid prototyping to delivery-ready pipelines
- **Physical Computing Solutions:** South African education (see [saml.co.za](https://saml.co.za))
- **Cloud-AI Integration:** AWS, Azure, Google, open source

---

## 🏆 Highlights

- **Member:** [TMG Makerspace Africa](https://tmgmakerspace.africa)
- **Key Projects:** [SAM-LMS Curriculum](https://saml.co.za), [mini-omni](https://github.com/gpt-omni/mini-omni), resource optimisation tools
- **Advocate for local innovation** – Building tech for real SA challenges

---

## 🛠️ Tech Stack

**Python, Node.js, FAST API, MLflow, Docker, AWS, Azure, GCP, HuggingFace, Kubernetes, OpenAI, Data Science**

---

## ✉️ Connect

- [sudhir@saml.co.za](mailto:sudhir@saml.co.za) • [LinkedIn](https://www.linkedin.com/in/sudhirdpn) • [X: @sudzdpn](https://x.com/sudzdpn)

---

## 📚 Impact Areas

- **Education:** Bridging digital divides through open-source curriculum and physical computing
- **AI for Africa:** Technical debt, resource efficiency, community-scale deployment
- **POPIA-Ready Data Engineering**

---

> **Let's collaborate to build real-world solutions for Africa — not just prototypes.**

---

## 🔒 Security Advisory Workflow

### Overview

This repository uses GitHub's Security Advisory feature to manage and document security vulnerabilities responsibly. This section provides a complete workflow for creating, managing, and documenting security advisories.

### Creating a Security Advisory Draft

#### Step 1: Access the Security Tab

1. Navigate to your test repository on GitHub
2. Click on the **Security** tab in the repository navigation
3. Click on **Advisories** under the "Reporting" section
4. Click **New draft security advisory**

#### Step 2: Complete the Advisory Template

Fill in all required fields with the following information:

**1. Title**
- Provide a clear, concise title that describes the vulnerability
- Example: "SQL Injection Vulnerability in User Authentication Module"

**2. Description**

Structure your description using the following sections:

```markdown
### Impact
- What kind of vulnerability is it?
- Who is impacted?
- What can attackers do with this vulnerability?
- Describe potential data exposure or system compromise

### Steps to Reproduce
1. Detailed step-by-step instructions
2. Include specific URLs, parameters, or code snippets
3. Provide example payloads if applicable
4. Document expected vs. actual behavior
5. Include any prerequisites or setup requirements

### Patches
- Has the problem been patched?
- What versions should users upgrade to?
- Describe the fix implementation (e.g., prepared statements, input validation)

### Workarounds
- Is there a way for users to fix or remediate the vulnerability without upgrading?
- Provide temporary mitigation steps
- Include configuration changes, WAF rules, or other protective measures

### Recommended Patch
- Specific version to upgrade to
- Implementation details of the fix
- List of security improvements included

### Credits
- Acknowledge security researchers who discovered the vulnerability
- Thank contributors who helped with remediation

### References
- Links to relevant security resources (OWASP, CWE, etc.)
- Related documentation or security guides
- Additional context or learning materials
```

**3. Affected Product**
- **Ecosystem**: Select from dropdown (npm, pip, Maven, etc.)
- **Package Name**: Enter the exact package name
- **Affected Versions**: Use semantic versioning (e.g., "< 2.1.0")
- **Patched Versions**: Specify fixed versions (e.g., ">= 2.1.0")

**4. Severity**
- Select from: Low, Moderate, High, or Critical
- Or use CVSS v3/v4 calculator for precise scoring
- Consider: Exploitability, Impact, Scope, Privileges Required

**5. Common Weakness Enumerator (CWE)**
- Enter the CWE ID (e.g., "CWE-89" for SQL Injection)
- Search and select from the dropdown
- Multiple CWEs can be added if applicable

**6. Credits**
- Add contributors by username, full name, or email
- Select credit type:
  - **Finder**: Discovered the vulnerability
  - **Reporter**: Reported the vulnerability
  - **Analyst**: Analyzed the vulnerability
  - **Coordinator**: Coordinated disclosure
  - **Remediation Developer**: Developed the fix
  - **Remediation Reviewer**: Reviewed the fix
  - **Remediation Verifier**: Verified the fix
  - **Other**: Other contributions

**7. CVE Identifier**
- Choose "Request CVE ID later" for GitHub to assign one
- Or select "I have an existing CVE ID" if already assigned

#### Step 3: Save as Draft

1. Review all fields for accuracy and completeness
2. Click **Create draft security advisory**
3. The advisory will be saved as a draft (not published)
4. You'll receive a unique GitHub Security Advisory ID (e.g., GHSA-xxxx-xxxx-xxxx)

### Managing Draft Advisories

#### Viewing Drafts

- Navigate to **Security** → **Advisories**
- View tabs: **Draft** | **Published** | **Closed**
- Click on any draft to view or edit

#### Collaborating on Drafts

- Add collaborators to discuss the vulnerability privately
- Create a temporary private fork to develop and test fixes
- Use the advisory discussion thread for coordination

#### Publishing an Advisory

**⚠️ Warning**: Publishing makes the advisory public. Only publish when:
- A fix is available and tested
- Users have been notified
- You're ready for public disclosure

**Publishing Steps**:
1. Open the draft advisory
2. Review all information for accuracy
3. Click **Publish advisory**
4. GitHub will automatically:
   - Assign a CVE ID (if requested)
   - Add the advisory to the GitHub Advisory Database
   - Create a security alert for dependent repositories

### Security Advisory Template Example

```markdown
Title: SQL Injection Vulnerability in User Authentication Module

### Impact
This vulnerability allows attackers to execute arbitrary SQL commands through 
improperly sanitized user input in the authentication module. All users of 
versions prior to 2.1.0 are affected. An attacker could gain unauthorized 
access, extract sensitive data, modify database records, or perform privilege 
escalation.

### Steps to Reproduce
1. Navigate to the login page at `/auth/login`
2. Enter a malicious SQL payload in the username field: `admin' OR '1'='1' --`
3. Enter any value in the password field
4. Submit the form
5. Observe successful authentication bypass and unauthorized access

### Patches
The vulnerability has been patched in version 2.1.0. Users should upgrade to 
version 2.1.0 or later immediately. The fix implements prepared statements and 
parameterized queries for all database interactions in the authentication module.

### Workarounds
If immediate upgrade is not possible:
1. Implement a Web Application Firewall (WAF) with SQL injection detection rules
2. Add input validation middleware to reject requests containing SQL metacharacters
3. Enable additional logging to monitor for suspicious authentication attempts
4. Restrict database user permissions to minimize potential damage

### Recommended Patch
Upgrade to version 2.1.0 which includes:
- Parameterized queries using prepared statements
- Input sanitization using database escaping functions
- Additional input validation layers
- Enhanced logging of authentication attempts

### Credits
Special thanks to security researcher Jane Doe for responsibly disclosing this 
vulnerability.

### References
- [OWASP SQL Injection Guide](https://owasp.org/www-community/attacks/SQL_Injection)
- [CWE-89: SQL Injection](https://cwe.mitre.org/data/definitions/89.html)
- [GitHub Security Advisory Guidelines](https://docs.github.com/en/code-security/security-advisories)

---
Ecosystem: npm
Package: example-auth-module
Affected Versions: < 2.1.0
Patched Versions: >= 2.1.0
Severity: High (7.0 - 8.9)
CWE: CWE-89 (SQL Injection)
Credit: janedoe (Finder)
```

### Best Practices

1. **Keep Drafts Confidential**: Don't share draft advisory links publicly
2. **Responsible Disclosure**: Give maintainers time to fix before publishing
3. **Clear Communication**: Use precise, technical language in descriptions
4. **Version Specificity**: Always specify exact affected and patched versions
5. **Complete Documentation**: Include all template sections for clarity
6. **Test Patches**: Verify fixes before publishing advisories
7. **Credit Researchers**: Always acknowledge security researchers properly
8. **Regular Reviews**: Periodically review and update draft advisories
9. **Security First**: Never publish advisories without fixes available
10. **Follow Standards**: Use CWE classifications and CVSS scoring

### Quick Reference Links

- [GitHub Security Advisories Documentation](https://docs.github.com/en/code-security/security-advisories)
- [CWE Database](https://cwe.mitre.org/)
- [CVSS Calculator](https://www.first.org/cvss/calculator/3.1)
- [OWASP Vulnerability Guide](https://owasp.org/www-community/vulnerabilities/)
- [CVE Numbering Authority](https://www.cve.org/)

### Sample Advisory Created

A sample security advisory has been created in this repository:
- **Advisory ID**: GHSA-v5c4-4mp3-hf68
- **Status**: Draft (not published)
- **Location**: Security → Advisories → Draft
- **Purpose**: Reference implementation and safe practice template

---

[TMG Makerspace Africa](https://tmgmakerspace.africa) | [SAM-LMS](https://saml.co.za)

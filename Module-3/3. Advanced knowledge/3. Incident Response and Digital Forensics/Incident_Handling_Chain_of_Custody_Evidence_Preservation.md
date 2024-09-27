
# Incident Handling: Chain of Custody and Evidence Preservation

## Introduction
In incident handling, ensuring that evidence is collected, preserved, and documented correctly is crucial for maintaining the integrity of a forensic investigation. The **chain of custody** is the chronological documentation of evidence, detailing who collected, handled, or transferred it. **Evidence preservation** ensures that the collected evidence remains intact and uncontaminated throughout the investigation.

---

## Scenario 1: Cyberattack Investigation

### Step 1: Chain of Custody

**Objective**: Track and document all interactions with digital evidence.

#### Definition:
The **chain of custody** ensures the integrity of evidence by recording every individual who handles it. This prevents allegations of tampering or contamination.

#### Key Components:
1. **Documentation**: Record details whenever evidence is collected or transferred.
2. **Transfer of Custody**: Each time evidence is transferred, document the recipient and purpose.
3. **Storage**: Securely store evidence to prevent unauthorized access.
4. **Integrity Verification**: Use cryptographic hash values (e.g., MD5) to confirm the evidence's integrity.

#### Steps:
1. **Collect Evidence**: Label, tag, and document digital evidence such as hard drives or memory.
2. **Document Chain of Custody**: Record each step in a chain-of-custody form.
3. **Transfer and Secure Storage**: Store evidence in a controlled environment, ensuring proper documentation of access.
4. **Integrity Verification**: Hash the evidence at the point of collection and verify the hash when transferred.

#### Deep Dive:
The chain of custody is critical to maintaining the credibility of the investigation. Any break in the chain can lead to questions about the authenticity of the evidence.

#### Outcome:
You collect and securely store digital evidence while maintaining a clear chain of custody, ensuring its credibility in legal or internal proceedings.

---

### Step 2: Evidence Preservation

**Objective**: Preserve the integrity of digital evidence and ensure it remains unchanged.

#### Definition:
**Evidence preservation** involves safeguarding digital evidence to prevent contamination or alteration. This includes creating forensic images and using cryptographic hashes to verify data integrity.

#### Key Components:
1. **Forensic Imaging**: Create bit-by-bit copies of digital evidence.
2. **Hashing**: Use cryptographic hashes to ensure the evidence remains unchanged.
3. **Write-Protection**: Use write-blockers to prevent accidental modifications.
4. **Secure Storage**: Store evidence in controlled environments with restricted access.

#### Steps:
1. **Forensic Imaging**: Create a bit-by-bit copy of the digital evidence.
2. **Use Write-Blockers**: Attach write-blockers to prevent any modification to the evidence.
3. **Hash the Data**: Calculate and verify cryptographic hash values to confirm the data's integrity.
4. **Long-Term Storage**: Store both the original evidence and forensic images in secure, access-controlled environments.

#### Deep Dive:
Forensic imaging allows investigators to work on a duplicate of the evidence, preventing accidental modification of the original. Hashing verifies that the evidence remains unchanged during the process.

#### Outcome:
Evidence is preserved through forensic imaging, write-blocking, and secure storage, ensuring its integrity throughout the investigation.

---

## Additional Practical Scenarios

### Scenario 2: Investigating Unauthorized Access

**Objective**: Investigate unauthorized network access while preserving logs and digital evidence.

#### Steps:
1. **Log Collection**: Collect logs from firewalls, servers, and workstations.
2. **Forensic Imaging**: Create forensic images of the compromised systems.
3. **Chain of Custody**: Document each step, from log collection to forensic imaging.
4. **Storage**: Store logs and forensic images in a secure environment.

#### Outcome:
The chain of custody is maintained, and the logs reveal the source and methods used for unauthorized access.

---

### Scenario 3: Employee Misconduct Investigation

**Objective**: Investigate potential employee misconduct involving the misuse of company assets.

#### Steps:
1. **Seize Devices**: Collect the employee’s laptop and any external storage.
2. **Forensic Imaging**: Create a forensic image of the laptop’s hard drive.
3. **Chain of Custody**: Document each step from evidence collection to analysis.
4. **Evidence Preservation**: Secure the original devices and forensic images in a controlled environment.

#### Outcome:
Evidence reveals the employee accessed sensitive company files, and the chain of custody confirms the evidence's authenticity.

---

### Scenario 4: Insider Threat Detection

**Objective**: Investigate an internal user suspected of exfiltrating sensitive data.

#### Steps:
1. **Forensic Imaging**: Create an image of the suspect’s workstation and associated devices.
2. **Use Hashing**: Calculate hash values of the collected data to ensure no tampering.
3. **Preserve Evidence**: Store the forensic images and original data in a secure, access-controlled environment.
4. **Log Analysis**: Analyze logs to detect any suspicious access or file transfers.

#### Outcome:
The investigation confirms that the insider exfiltrated data via unauthorized network access, and the chain of custody ensures the integrity of the evidence.

---

## Conclusion
Incident handling requires a strict adherence to the processes of **chain of custody** and **evidence preservation**. By documenting each step and using forensic imaging, hashing, and secure storage, investigators can maintain the integrity and credibility of the evidence throughout the investigation.

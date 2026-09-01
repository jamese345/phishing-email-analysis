# Phishing Email Analysis — Banco do Bradesco Impersonation

## Overview

The objective was to analyze a suspicious email claiming to originate from Banco do Bradesco and determine whether it was legitimate or part of a phishing campaign — a routine but critical Tier 1 SOC task, since misjudging one of these can lead to credential theft or a successful business email compromise.

## Investigation Scope

- Email header analysis
- Authentication validation (SPF, DKIM, DMARC)
- IOC extraction
- URL analysis
- Threat intelligence enrichment
- Infrastructure investigation
- MITRE ATT&CK mapping

## Tools Used

- EML Analyzer
- MXToolbox
- VirusTotal
- Manual header analysis
- Threat intelligence techniques

## Investigation Workflow

1. Acquired the raw EML file.
2. Extracted email headers.
3. Validated SPF, DKIM, and DMARC records.
4. Identified sender infrastructure.
5. Extracted URLs and domains.
6. Performed VirusTotal reputation analysis.
7. Collected indicators of compromise.
8. Mapped activity to MITRE ATT&CK.
9. Produced an investigation report.

## Findings

![Raw EML file](Screenshots/raw%20eml.png)
*The raw EML file acquired for analysis.*

![EML Analyzer header breakdown](Screenshots/EML%20Analyzer.png)
*Header breakdown from EML Analyzer showing the authentication failures below.*

![MXToolbox SPF/DKIM/DMARC check](Screenshots/MX%20Toolbox.png)
*MXToolbox validation confirming the SPF, DKIM, and DMARC failures.*

![VirusTotal lookup for sending IP](Screenshots/Virustotal%20for%20IP.png)
*Reputation lookup on the sending IP, tying back to the DigitalOcean-hosted infrastructure.*

![VirusTotal lookup for suspicious domain](Screenshots/Virustotal%20for%20domain.png)
*Reputation lookup on the suspicious sending domain.*

### Authentication Failures
- DKIM signature missing
- SPF validation failure
- DMARC validation failure

### Infrastructure Indicators
- **Sending IP:** 137.184.34.4
- **Hosting provider:** DigitalOcean LLC

### Suspicious Domain
`blog1seguimentmydomaine2bra.me`

### Social Engineering Tactics
- Urgency
- Reward-based incentive
- Account action pressure
- Loyalty points expiration

## MITRE ATT&CK Mapping

| Technique | ID |
|---|---|
| Phishing | T1566 |
| Spearphishing Link | T1566.002 |
| Masquerading | T1036 |
| User Execution | T1204 |

## Final Verdict

**HIGH CONFIDENCE PHISHING EMAIL.** The message exhibits multiple indicators associated with phishing campaigns, including authentication failures, suspicious hosting infrastructure, and social engineering techniques designed to pressure quick action.

## Impact

Correctly flagging this as phishing before a user clicks the link or enters credentials prevents account compromise and stops the domain from being used as a foothold for further attacks against the organization.

## Next Steps

- Submit the sending IP and domain for blocklisting.
- Search mail logs for other recipients of the same campaign.
- Add the DKIM/SPF/DMARC failure pattern as a detection rule for future similar attempts.

---
*Part of my hands-on SOC analyst project portfolio — see my [profile README](https://github.com/jamese345) for more.*



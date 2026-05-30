# phishing-email-analysis

The objective was to analyze a suspicious email claiming to originate from Banco do Bradesco and determine whether it was legitimate or part of a phishing campaign.

The investigation involved:

* Email header analysis
* Authentication validation (SPF, DKIM, DMARC)
* IOC extraction
* URL analysis
* Threat intelligence enrichment
* Infrastructure investigation
* MITRE ATT&CK mapping

## Tools Used

* EML Analyzer
* MXToolbox
* VirusTotal
* Manual Header Analysis
* Threat Intelligence Techniques
* 
## Investigation Workflow

1. Acquired raw EML file.
2. Extracted email headers.
3. Validated SPF, DKIM, and DMARC records.
4. Identified sender infrastructure.
5. Extracted URLs and domains.
6. Performed VirusTotal reputation analysis.
7. Collected indicators of compromise.
8. Mapped activity to MITRE ATT&CK.
9. Produced investigation report.

## Key Findings

### Authentication Failures

* DKIM Signature Missing
* SPF Validation Failure
* DMARC Validation Failure

### Infrastructure Indicators

Sending IP:

137.184.34.4

Hosting Provider:

DigitalOcean LLC

### Suspicious Domain

blog1seguimentmydomaine2bra.me

### Social Engineering Tactics

* Urgency
* Reward-based incentive
* Account action pressure
* Loyalty points expiration


## MITRE ATT&CK

| Technique          | ID        |
| ------------------ | --------- |
| Phishing           | T1566     |
| Spearphishing Link | T1566.002 |
| Masquerading       | T1036     |
| User Execution     | T1204     |

## Final Verdict

HIGH CONFIDENCE PHISHING EMAIL

The message exhibits multiple indicators associated with phishing campaigns including authentication failures, suspicious infrastructure, and social engineering techniques.



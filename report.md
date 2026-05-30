# Investigation Methodology

## Step 1 – Obtain Raw Email

Acquired a suspicious .eml file for analysis.

Goal:

Determine whether the email was legitimate or malicious.

---

## Step 2 – Analyze Email Contents

Loaded the email into EML Analyzer.

Collected:

* Subject
* Sender Address
* Recipient
* URLs
* Domains
* HTML Content

Observation:

The email claimed to be from Banco do Bradesco and urged immediate action.

---

## Step 3 – Extract Email Headers

Reviewed:

* Message-ID
* Return-Path
* Received Headers
* Authentication Results

Purpose:

Trace email origin and validate authenticity.

---

## Step 4 – Validate SPF

Finding:

SPF returned TempError.

This indicates sender validation issues and lowers trust in the message.

---

## Step 5 – Validate DKIM

Finding:

No DKIM signature found.

Legitimate organizations typically sign outbound email.

---

## Step 6 – Validate DMARC

Finding:

DMARC validation failed.

The message could not be verified as originating from the claimed sender.

---

## Step 7 – Identify Infrastructure

Extracted sending IP:

137.184.34.4

Identified hosting provider:

DigitalOcean

Observation:

Infrastructure did not resemble expected banking email systems.

---

## Step 8 – Analyze Embedded URLs

Extracted:

blog1seguimentmydomaine2bra.me

Observation:

Domain was unrelated to official Bradesco infrastructure.

---

## Step 9 – Threat Intelligence Enrichment

Used VirusTotal to investigate:

* Domain reputation
* IP reputation
* Related indicators

Observation:

The domain had little detection history, but the IP showed suspicious activity.

---

## Step 10 – Collect Indicators of Compromise

Documented:

* Email address
* Domain
* URL
* IP Address
* Subject line

---

## Step 11 – MITRE ATT&CK Mapping

Mapped attacker behavior to:

* T1566
* T1566.002
* T1036
* T1204

---

## Step 12 – Final Classification

Based on the collected evidence, the email was classified as:

PHISHING (HIGH CONFIDENCE)

---
title: FAQ
permalink: /faq/
---

### What is HealthCerts?
HealthCerts is a set of digital standards and schema for issuing digital COVID-19 test results certificates that are in line with international standards and the Singapore Government’s requirements. 

### Who developed HealthCerts?
HealthCerts schema was developed in collaboration with Government Technology Agency and Ministry of Health, Singapore.

### Where should I verify HealthCerts?
"Non-Notarised HealthCerts
These are typically issued by clinics, after the tests have been performed. Verification can be performed at the verifier site of the respective certificate issuers. Alternatively, a non-notarised HealthCert which is compatible to the Open Attestation format, can be verified in https://opencerts.io. 
 
Notarised HealthCerts
HealthCerts that had been notarised [here](https://notarise.gov.sg), can be verified at [https://verify.gov.sg](https://verify.gov.sg)."

### What is the format of the QR implementation?
The QR code shall contain the following components:
i. A link to fetch the HealthCert
ii. Decryption key to decrypt HealthCert payload
iii. URL to perform verification of HealthCert

Key properties:
Encryption shall be performed using oa-encrypt
QR code shall be readable by any standard QR code reader (non-proprietary
formatting)

### How do i join the HealthCerts Community?
You can join this [Telegram channel](https://t.me/joinchat/GOgThBo8L3qhefgIVjZ-EA) for the latest updates and developments on HealthCerts.

### Where can I find the list of clinics approved to perform Covid tests?
You may find the list of approved clinics [here](https://go.gov.sg/covid19pcrtestproviders).

## HealthCerts Schema

### Can I issue a digital certificate with different data fields from the defined schema?
All mandatory fields need to be included.
You may choose to omit optional fields.
You may add more data fields, than listings in the schema, in your digital certificate, but the data may not be included in the Notarized HealthCert.

### Where can i view a copy of the schema?
You may find a copy of the HealtCert schema at [https://healthcerts.gov.sg/schema/](https://healthcerts.gov.sg/schema/)
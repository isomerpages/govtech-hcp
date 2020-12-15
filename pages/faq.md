---
title: FAQ
permalink: /faq/
---

#### What is HealthCerts?
HealthCerts is a set of digital standards and schema for issuing digital COVID-19 test results certificates that are in line with international standards and the Singapore Government’s requirements. 

#### Who developed HealthCerts?
HealthCerts schema was developed in collaboration with Government Technology Agency and Ministry of Health, Singapore.

<!-- #### Where should I verify HealthCerts?
**Non-Notarised HealthCerts**<br>
These are typically issued by clinics, after the tests have been performed. Verification can be performed at the verifier site of the respective certificate issuers. Alternatively, a non-notarised HealthCerts which is compatible to the Open Attestation format, can be verified in <a target="_blank" href="https://opencerts.io"> https://opencerts.io </a>. 
 
**Notarised HealthCerts**<br>
HealthCerts that had been notarised <a target="_blank" href="https://notarise.gov.sg"> here </a>, can be verified at <a target="_blank" href="https://verify.gov.sg">https://verify.gov.sg </a>. -->

#### What is the format of the QR implementation?
The QR code shall contain the following components:
<ol class="roman"> 
<li>A link to fetch the HealthCerts</li>
<li>Decryption key to decrypt HealthCerts payload</li>
<li>URL to perform verification of HealthCerts</li>
</ol>


**Key properties:**
Encryption shall be performed using oa-encrypt
QR code shall be readable by any standard QR code reader (non-proprietary
formatting)

#### How do i join the HealthCerts Community?
You can join this <a target="_blank" href="https://t.me/joinchat/GOgThBo8L3qhefgIVjZ-EA">Telegram channel </a> for the latest updates and developments on HealthCerts.

#### Where can I find the list of clinics approved to perform Covid tests?
You may find the list of approved clinics <a target="_blank" href="https://go.gov.sg/covid19pcrtestproviders">here</a>.

## HealthCerts Schema

#### Can I issue a digital certificate with different data fields from the defined schema?
All mandatory fields need to be included.
You may choose to omit optional fields.
<!-- You may add more data fields, than listings in the schema, in your digital certificate, but the data may not be included in the Notarized HealthCert. -->
You may add more data fields, than listings in the schema, in your digital certificate, but the data may not be included in the HealthCerts.

#### Where can i view a copy of the schema?
You may find a copy of the HealthCerts schema  <a target="_blank" href="https://healthcerts.gov.sg/schema/">here</a>
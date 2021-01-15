---
title: Digital Standards
permalink: /digital-standards/
---
<style type="text/css">

ol.letter{
    list-style-type: lower-alpha;
}

ol.roman{
    list-style-type: lower-roman;
}

ol.upper-roman{
    list-style-type: upper-roman;
}

</style>

<p>Updated 11th Jan 2021</p>

## Key Attributes
<ol class="letter"> 
<li>Interoperability</li>
<li>Verifiable</li>
<li>Secure (Tamper-proof)</li>
<li>Scalable</li>
</ol>

## Presentation


HealthCerts shall comprise of the data elements defined in the schema.
During presentation, these are the minimum data types that need to be displayed.

<ol class="upper-roman"> 
<li>Data fields as defined in <a href="https://schemata.openattestation.com/" target="_blank">schema</a><br></li>   
<li>QR code<br></li>   
<ol class="letter">
<li>  The QR code shall contain the following components:</li>
<ol class="roman">
<li>A link to fetch the HealthCert</li>
<li>Decryption key to decrypt HealthCert payload</li>
<li>URL to perform verification of HealthCert</li>
<li>Encryption shall be based performed using <a href="https://github.com/Open-Attestation/oa-encryption/blob/master/src/index.ts" target="_blank">oa-encrypt</a><br></li>
</ol>
<li>QR code shall be readable by any standard QR code reader (non-proprietary formatting)</li>
</ol>
</ol>
<br> 
This requirement for shall apply to the various modes of certificate delivery, which could include sharing via
<br>
<ol class="roman">
<li>HealthCerts document<a href="#def1"><sup>1</sup></a> which contains the memo and QR code</li>
<li>Mobile application which renders the HealthCerts document in (i)
Refer <a href="https://github.com/Open-Attestation/adr/blob/master/decentralised_rendering.md" target="_blank">here</a> for details.</li>
<li>Email which contains the memo and QR code</li>
</ol>


## Verification

The verifier shall attest the following datasets

<div style="padding:0 50px">
<h4>1. ISSUER_IDENTITY</h4>
<p>Checks and returns the identity of the issuer. Verify the identity of the issuer against a decentralised identity provider (ie DID, DNS, etc) or some centrally managed identity registry.</p>
<h4>2. DOCUMENT_INTEGRITY </h4>
<p>Checks the integrity of the document by digesting the content of the OA document and comparing it with the document's targetHash</p>
<h4>3. DOCUMENT_STATUS</h4>
<p>Checks that the document has been issued and that it\'s issuance status is in good standing. Verify the issuance status against a record maintained externally, ie Records on a Blockchain or API endpoints.</p>
<div>

<hr>

<div><b>Footnotes</b></div>
<br>
<a id="def1" style="padding-top:50px"></a>

1.Documents shall be verifiable on <a href="https://opencerts.io" target="_blank">https://opencerts.io</a>
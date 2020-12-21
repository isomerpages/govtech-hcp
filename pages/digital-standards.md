---
title: Digital Standards v4.1
permalink: /digital-standards/
---
<style type="text/css">

ol.letter{
    list-style-type: upper-alpha;
}

ol.roman{
    list-style-type: lower-roman;
}


</style>

## Key Attributes
<ol class="letter"> 
<li>Interoperability</li>
<li>Verifiable</li>
<li>Secure (Tamper-proof)</li>
<li>Scalable</li>
</ol>

## Presentation

Two modes of presentation shall be made available to the document bearers

1. <a href="https://github.com/Open-Attestation/adr/blob/master/universal_actions.md" target="_blank">QR code</a>
    
    <ol class="letter"> 
    <li>The QR code shall contain the following components:<br></li>   
    <ol class="roman">
    <li>  A link to fetch the HealthCerts</li>
    <li>Decryption key to decrypt HealthCerts payload </li>
    <li>URL to perform verification of HealthCerts </li>
    <li>Encryption shall be based performed using <a href="https://github.com/Open-Attestation/oa-encryption/blob/master/src/index.ts" target="_blank">oa-encrypt</a><br></li>
    </ol>
    <li>QR code shall be readable by any standard QR code reader (non-proprietary formatting)<br><br></li>
    </ol>
    
2.  Rendering of document on a Mobile App

Refer <a href="https://github.com/Open-Attestation/adr/blob/master/decentralised_rendering.md" target="_blank">here</a> for details.

## Verification

The verifier shall attest the following datasets

### 1. ISSUER_IDENTITY

Checks and returns the identity of the issuer. Verify the identity of the issuer against a decentralised identity provider (ie DID, DNS, etc) or some centrally managed identity registry.

### 2. DOCUMENT_INTEGRITY 

Checks the integrity of the document by digesting the content of the OA document and comparing it with the document\'s targetHash

### 3. DOCUMENT_STATUS

Checks that the document has been issued and that it\'s issuance status is in good standing. Verify the issuance status against a
record maintained externally, ie Records on a Blockchain or API endpoints.


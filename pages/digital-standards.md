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
    <li>  A link to fetch the HealthCert</li>
    <li>Decryption key to decrypt HealthCert payload </li>
    <li>URL to perform verification of HealthCert </li>
    <li>Encryption shall be based performed using <a href="https://github.com/Open-Attestation/oa-encryption/blob/master/src/index.ts" target="_blank">oa-encrypt</a><br><br></li>
    </ol>
    <li>QR code shall be readable by any standard QR code reader (non-proprietary formatting)<br></li>
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

## Appendix A - Schema

```json
{
    "id": "TEST001",
    "name": "HealthCert",
    "$template": {
        "name": "HealthCert_v1.0",
        "type": "EMBEDDED_RENDERER",
        "url": "https://render.openattestation.io"
    },
    "issuers": [
        {
            "name": "IssuerCompanyName",
            "documentStore": "0x0B209E53aaae5E9744d70509b74d66358df0bb27",
            "network": "ETHEREUM",
            "identityProof": {
                "type": "DNS-TXT",
                "location": "ropstore.openattestation.io"
            }
        }
    ],
    "fhirVersion": "4.0.1",
    "fhirBundle": {
        "resourceType": "Bundle",
        "type": "collection",
        "entry": [
            {
                "resourceType": "Patient",
                "extension": [
                    {
                        "url": "http://hl7.org/fhir/StructureDefinition/patient-nationality",
                        "code": {
                            "text": "SG"
                        }
                    }
                ],
                "identifier": [
                    {
                        "type": "PPN",
                        "value": "E7831177G"
                    },
                    {
                        "type": {
                            "text": "NRIC"
                        },
                        "value": "S9098989Z"
                    }
                ],
                "name": [
                    {
                        "text": "Tan Chen Chen"
                    }
                ],
                "gender": "female",
                "birthDate": "1990-01-15"
            },
            {
                "resourceType": "Specimen",
                "type": {
                    "coding": [
                        {
                            "system": "http://snomed.info/sct",
                            "code": "258500001",
                            "display": "Nasopharyngeal swab"
                        }
                    ]
                },
                "collection": {
                    "collectedDateTime": "2020-09-27T06:15:00Z"
                }
            },
            {
                "resourceType": "Observation",
                "identifier": [
                    {
                        "value": "123456789",
                        "type": "ACSN"
                    }
                ],
                "code": {
                    "coding": [
                        {
                            "system": "http://loinc.org",
                            "code": "94531-1",
                            "display": "Reverse transcription polymerase chain reaction (rRT-PCR) test"
                        }
                    ]
                },
                "valueCodeableConcept": {
                    "coding": [
                        {
                            "system": "http://snomed.info/sct",
                            "code": "260385009",
                            "display": "Negative"
                        }
                    ]
                },
                "effectiveDateTime": "2020-09-28T06:15:00Z",
    “status”: “final”,
                "performer": {
                    "name": [
                        {
                            "text": "Dr Michael Lim"
                        }
                    ]
                },
                "qualification": [
                    {
                        "identifier": "MCR 123214",
                        "issuer": "MOH"
                    }
                ]
            },
            {
                "resourceType": "Organization",
                "name": "MacRitchie Medical Clinic",
                "type": "Licensed Healthcare Provider",
                "endpoint": {
                    "address": "https://www.macritchieclinic.com.sg"
                },
                "contact": {
                    "telecom": [
                        {
                            "system": "phone",
                            "value": "+6563113111"
                        }
                    ],
                    "address": {
                        "type": "work",
                        "use": "physical",
                        "text": "MacRitchie Hospital Thomson Road Singapore 123000"
                    }
                }
            },
            {
                "resourceType": "Organization",
                "name": "MacRitchie Laboratory",
                "type": "Accredited Laboratory",
                "contact": {
                    "telecom": [
                        {
                            "system": "phone",
                            "value": "+6562711188"
                        }
                    ],
                    "address": {
                        "type": "work",
                        "use": "physical",
                        "text": "2 Thomson Avenue 4 Singapore 098888"
                    }
                }
            }
        ]
    }
}
```

# Credential Lifecycle
A credential is a set of one or more claims made by the same entity. Credentials might also include an identifier and metadata to describe properties of the credential, such as the issuer, the expiry date and time, a representative image, a public key to use for verification purposes, the revocation mechanism, and so on. The metadata might be signed by the issuer. A verifiable credential is a set of tamper-evident claims and metadata that cryptographically prove who issued it.

Examples of verifiable credentials include digital employee identification cards, digital birth certificates, and digital educational certificates. 

### Lorena Credentials

We have defined three type of credentials:

#### Verifiable Credential

```json
{
    "@context": [ "https://www.w3.org/2018/credentials/v1" ],
    "type": ["VerifiableCredential"],
    "issuer": "",
    "issuanceDate": "",
    "credentialSubject": "",
    "proof": {
        "type" : "Curve448-Goldilocks",
        "proofPurpose":"assertionMethod",
        "verificationMethod": "",
        "signature": ""
    }
}
```

#### Organization Role

```json
{
    "@type": "OrganizationRole",
    "roleName": "",
    "member": {
        "@type": "Person",
        "id": "",
        "givenName": "",
        "familyName" : "",
        "additionalName" : "",
        "identifier": {
            "@type":"PropertyValue",
            "propertyID": "",
            "value":  ""
        }
    }
}
```

#### Create Action

```json
{
    "@type": "CreateAction",
    "id": "",
    "name": "",
    "description": "",
    "agent": {
        "@type": "Person",
        "id": ""
    },
    "location": {
        "@type": "Residence",
        "name": ""
    },
    "potentialAction": ""
}
```

## Credentials types

Software systems that process the kinds of objects specified in this document use type information to determine whether or not a provided verifiable credential or verifiable presentation is appropriate. This specification defines a type property for the expression of type information. 

### Standards W3C
| Object | Type |
| -- | -- | 
| Verifiable credential object (a subclass of a credential object)  | VerifiableCredential and, optionally, a more specific verifiable credential type. For example, ```"type": ["VerifiableCredential", "UniversityDegreeCredential"] ```|
| Credential object  | VerifiableCredential and, optionally, a more specific verifiable credential type. For example, ```"type": ["VerifiableCredential", "UniversityDegreeCredential"]``` | 
| Verifiable presentation object (a subclass of a presentation object)  | VerifiablePresentation and, optionally, a more specific verifiable presentation type. For example, ```"type": ["VerifiablePresentation", "CredentialManagerPresentation"]``` | 
| Presentation object  | VerifiablePresentation and, optionally, a more specific verifiable presentation type. For example, ```"type": ["VerifiablePresentation", "CredentialManagerPresentation"] ```| 
| Proof object  | A valid proof type. For example, ```"type": "RsaSignature2018"``` | 
| credentialStatus object  | A valid credential status type. For example, ```"type": "CredentialStatusList2017"``` | 
| termsOfUse object  | A valid terms of use type. For example, ```"type": "OdrlPolicy2017") ```| 
| evidence object  | A valid evidence type. For example, ```"type": "DocumentVerification2018"``` | 

### Zenroom Proofs
For instance a proof can be print in JSON format and looks a bit list this:

```json
{
   "credential_proof" : {
      "pi_v" : {
         "c" : "u64:tBrCGawWYEAi55_hHIPq0JT3OaapOebSHVW0GhjJcAk",
         "rr" : "u64:J7R3FXsI2dcfyZRCqWA8fDYijG39P16LvGpX90wtCWw",
         "rm" : "u64:QoG-28CNTAY3Ir4SQqVoK1ZpTlzOnXxX6Xtq5KMIxpo"
      },
      "nu" : "u64:BA77WYvBRsc53uAyrqTjuUdptJPZbcTlzr9icizm0...",
      "sigma_prime" : {
         "h_prime" : "u64:BB9AM5xjWPxsZ47zh1WAmFymru66W6YuK...",
         "s_prime" : "u64:BAGYNM6JO0wRAGE87_-bQVuhUXeEoeJrh..."
      },
      "kappa" : "u64:GFVYsudbHOJNzPl3ZL0_VzB_DRvrPKF26OCZR9..."
   },
   "zenroom" : {
      "scenario" : "coconut", "encoding" : "url64", "version" : "1.0.0"
   }
}
```
Anyone can verify proofs using as input:

    - the credential proof
    - the verifier


The flow described above is pretty simple, but the steps to setup the credential are a bit more complex:
![Zenroom Proofs](../../images/zenroom-proofs.png)




<!-- 
## Issue

## Create

## Share

## Check

## Revoke

-->